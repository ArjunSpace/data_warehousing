Option A:

Strengths:

    This option allows for the scores to be stored as attributes of the Customer
    dimension, which will make it easy for users to filter or group by scores in their queries.
    It also avoids the need for additional dimensions or outrigger tables, which may simplify
    the overall design of the warehouse.
    
    
Weaknesses: 

    This option involves overwriting old scores with new scores when they
    change, which means that the warehouse will not retain a history of changes to
    customer scores. This may make it difficult for users to understand how and why a
    customer's score changes over time.
    
    
Option B:

Strengths: 

    This option allows for the retention of a history of changes to customer
    scores, which may be useful for analysis and understanding how scores change over
    time. It also allows for the scores to be stored as attributes of the Customer dimension,
    which will make it easy for users to filter or group by scores in their queries.
    
Weaknesses:

    This option requires the creation of new Customer dimension rows each
    time a score changes, which may increase the complexity and size of the dimension. It
    may also make it more difficult for users to identify the current score for a customer, as
    they will have to determine which row represents the most recent score.
    
Option C:

Strengths: 

    This option allows for the scores to be stored in a separate CustomerScores
    dimension, which may make it easier for users to filter or group by scores in their
    queries. It also allows for the retention of a history of changes to customer scores, as
    the fact table includes a foreign key to the CustomerScores dimension rather than the
    scores themselves.
    
Weaknesses:

    This option requires the creation of a separate CustomerScores
    dimension with 45 rows, which may increase the complexity of the warehouse design. It
    also requires the use of foreign keys in the fact table, which may make it more difficult
    to perform certain types of analysis.
    
Option D:

Strengths:

    This option allows for the scores to be stored in an outrigger table, which
    may make it easier for users to filter or group by scores in their queries. It also allows
    for the retention of a history of changes to customer scores, as the Customer
    dimension includes a foreign key to the outrigger table rather than the scores
    themselves.
    
Weaknesses:

    This option requires the use of an outrigger table, which may increase the
    complexity of the warehouse design. It also requires the use of foreign keys in the
    Customer dimension, which may make it more difficult to perform certain types of
    analysis.
 
---------------------------------------------------------------------------------------------------- 
      Given the options presented, I would choose Option B. This option allows for the
      retention of a history of changes to customer scores, which may be useful for analysis
      and understanding how scores change over time. It also allows for the scores to be
      stored as attributes of the Customer dimension, which will make it easy for users to
      filter or group by scores in their queries.
-----------------------------------------------------------------------------------------------------
    If the number of customers or the time interval between score recalculations was much
    larger, I would still choose Option B. This option allows for the retention of a history of
    changes to customer scores, which may be more useful for analysis and understanding
    how scores change over time when dealing with a larger number of customers or more
    frequent score recalculations.
    
    If the number of customers or the time interval between score recalculations was much
    smaller, I may consider Option A as well. In this case, the increased complexity and size
    of the Customer dimension associated with Option B may not be justified, as the
    number of changes to customer scores is likely to be much smaller.
    An alternative design that could be considered is to store the scores in a separate
    CustomerScores fact table with a grain of one row per customer. 
