# API Reference - Class qit.Qclient.Qclient 

## Qclient()

    Desc: init qindom client instance to use qit service
    In: 
        username: string, your username
        secrect_key: string, your secrect_key, or you can use token. If you use token, you cannot run get_token
    Out: object
    
<p>Sample code

    from qit.Qclient import Qclient
    username = "jimmy"
    secrect_key = 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
    client = Qclient(username,secrect_key)
    token = client.get_token()
    print(token)
    client2 = Qclient(username,token)

<p>Return
    
    388c0625b0f85e0efae3d070eaebed9145f4d0e4
    
## get_token()

    Desc: get token for current user, which will expire in designated time. You can use this token to use qit service temporarily
    In: na
    Out: string, token value
    
<p>Sample code

    from qit.Qclient import Qclient
    username = "jimmy"
    secrect_key = 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
    client = Qclient(username,secrect_key)
    token = client.get_token()
    print(token)
    client2 = Qclient(username,token)

<p>Return
    
    388c0625b0f85e0efae3d070eaebed9145f4d0e4

## get_methods()
    
    Desc: get the list of all the algorithms supported by Qit. At this time, qit supports supervised binary classification, will support more in the future
    In: na
    Out: string, names of algorithms
    
<p>Sample code
    
    from qit.Qclient import Qclient
    username = "jimmy"
    secrect_key = 'cd6214cd7b91518b9697983969ab34e17a47dd29'
    client = Qclient(username,secrect_key)
    print(np.array(client.get_methods()))


<p>Return

    '["ADA_BOOST","RANDOM_FOREST","QBOOST_IT","DECISION_TREE","GRADIENT_BOOST","K_NEIGHBORS","LOGIC_REGRESSION","XGBOOST","LIGHTGBM","INFINITY"]'
    
## train_model_s3()

    Desc: Train model on Qit
    In:
        training_data: string, the s3 path of training
        clf_type：string, the name of algorithm, in ["ADA_BOOST","RANDOM_FOREST","QBOOST_IT","DECISION_TREE","GRADIENT_BOOST","K_NEIGHBORS","LOGIC_REGRESSION","XGBOOST","LIGHTGBM","INFINITY"]
        Infinity is an algorithm developed by Qindom, Qboost_it is AutoML developed by Qindom. If you set clf_type as QBOOST_IT, qit will run and optimize all the algorithm automatically for you, and give you the best result.
        auto_adjust=True: Boolean, if Qit do hyperparameter optimization automatically or not
        n_estimators=None: int, paramater from sk-learn algorithm
        random_state=None: int, paramater from sk-learn algorithm
        max_depth=None: int, paramater from sk-learn algorithm
        lmd=None: Deprecation
        kernel=None: string, paramater from sk-learn algorithm
        n_neighbors=None: int,  paramater from sk-learn algorithm
        verbose=None: Boolean, paramater from sk-learn algorithm
        gamma=None, float, paramater from sk-learn algorithm
        c=None: float, paramater from sk-learn algorithm
    Out: dict, including model id
    
 <p>Sample code
    
    from qit.Qclient import Qclient
    username = "jimmy"
    secrect_key = 'cd6214cd7b91518b9697983969ab34e17a47dd29'
    client = Qclient(username,secrect_key)
    dataset='iris'
    model_id = client.train_model_s3(training_data=username +'/' + dataset + '_train_X_y.csv', clf_type='DECISION_TREE')
    print(model_id)
    print(model_id['body'])
    
<p>Return
    
    {'headers': {}, 'body': 142113, 'statusCodeValue': 200, 'statusCode': 'OK'}
    142113
    
## predict_sync()

    Desc: Do predict on Qit
    In:
        test_data: string, s3 path, should be like: "your username" + "/" + training data file name
        modelId: int, model id got from train_model_s3()
    Out: string, including prediction result. If you do predict after train right away, you may get 'Models are not ready yet' notification
        
<p>Sample code

    from qit.Qclient import Qclient
    username = "jimmy"
    secrect_key = 'cd6214cd7b91518b9697983969ab34e17a47dd29'
    client = Qclient(username,secrect_key)
    dataset='iris'
    model_id = client.train_model_s3(training_data=username +'/' + dataset + '_train_X_y.csv', clf_type='DECISION_TREE')
    prediction_result = client.predict_sync(test_data=username + '/' + dataset + '_valid_X.csv', modelId=model_id['body'])
    while 'Models are not ready yet' in prediction_result:
            print(prediction_result + ", will try after a minute")
            time.sleep(60)
            prediction_result = client.predict_sync(test_data=username + '/' + dataset + '_valid_X.csv', modelId=model_id['body'])
    print(prediction_result)
    predict_array = np.array(json.loads(prediction_result)['y_test_pred'])
    
<p>Return
    
    Models are not ready yet, will try after a minute
    {"y_test_pred":[[-1.0],[1.0],[1.0],[1.0],[1.0],[1.0],[-1.0],[1.0],[1.0],[-1.0],[1.0],[1.0],[1.0],[-1.0],[1.0],[1.0],[-1.0],[1.0],[-1.0],[-1.0],[-1.0],[1.0],[1.0],[1.0],[1.0],[1.0],[1.0],[1.0],[-1.0],[1.0],[1.0],[1.0],[-1.0],[1.0],[-1.0],[1.0],[-1.0],[-1.0],[1.0],[-1.0],[-1.0],[1.0],[-1.0],[-1.0],[1.0]]}
    
