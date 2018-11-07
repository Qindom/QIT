API Reference
===========================


# Class qit.Qclient.Qclient 
## get_methods()
    
    Desc: get the list of all the algorithms supported by Qit
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
    
