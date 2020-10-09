# Leetcode-Notebook

This Notebook provides insights and ideas for the practice problems in the leetcode. I will provide detail of the problem for following problems. Sign up Leetcode for details of the problems. 

# Combine 2 tables (1):

 

Write a SQL query for a report that provides the following information for each person in the Person table, regardless if there is an address for each of those people:

Answer:

Select Person.FirstName, Person.LastName, Address.City, Address.State from Person left outer join Address on Person.PersonId = Address.PersonId

Alternative answer:

Select Person.FirstName,Person.LastName,Address.City,Address.State from Person LEFT JOIN Address ON Person.PersonId = Address.PersonId (2) 

Pre_submitted solution:

Select Person.FirstName, Person.LastNmae, Address.City, Address.State from Person, Address where Person. (wrong)

# Knowledge Preliminary:

A out join B on A.a = B.a: Suppose the a is the primary id for A and reference id for b. Denoted the combined table as table c. The formula fixes all the attributes of a in A. Copies these attributes to Table c. Then, it goes through A.a[1], takes its relevant attribute and store in table c and then goes through B.a. It returns Null if there is no a[1] in B.a and return the relevant attributes if there is a[i] in B such that a[1] = a[i] where i is in Z Iterate the process untill A.a[n] where n is the last attribute in A.a. 

Default join in sql is the inner join. 

The reason we can't use inner join in this case is because the inner join will not return value that is null. In our case, if the person doesn't provide his address, he or she will not be shown in the combined table. 

Recap: Why does the pre_submitted solution fail?



# Reference:

(1) Leetcode, 10/9/2020, https://leetcode.com/problems/combine-two-tables/

(2) plabon,. 10/9/2020, https://leetcode.com/problems/combine-two-tables/discuss/879279/98-faster-then-mysql-users
