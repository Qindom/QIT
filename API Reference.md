API Reference
===========================


# Class qit.Qclient.Qclient 
## qit.Qclient.Qclient.get_methods()
    
    Desc: get the list of all the algorithms supported by Qit
    In: na
    Out: string
    
<p>Sample code
    
    from qit.Qclient import Qclient
    username = "jimmy"
    secrect_key = 'b4415bc3-b497-493d-9d1b-ad65beca5d44'
    client.get_methods()


<p>Return

    '["ADA_BOOST","RANDOM_FOREST","QBOOST_IT","DECISION_TREE","GRADIENT_BOOST","K_NEIGHBORS","LOGIC_REGRESSION","XGBOOST","LIGHTGBM","INFINITY"]'
    
## train_model_s3(training_data, clf_type, auto_adjust=True, n_estimators=None, random_state=None,
                       max_depth=None, lmd=None, kernel=None, n_neighbors=None, verbose=None, gamma=None, c=None)

