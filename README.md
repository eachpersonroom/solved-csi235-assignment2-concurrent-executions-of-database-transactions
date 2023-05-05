Download Link: https://assignmentchef.com/product/solved-csi235-assignment2-concurrent-executions-of-database-transactions
<br>
<h2>Task 1 Concurrent executions of database transactions</h2>

Consider the database transactions listed below.

<table width="413">

 <tbody>

  <tr>

   <td width="144"><u>T1         </u></td>

   <td width="144"><u>T2         </u></td>

   <td width="125"><u>T3        </u></td>

  </tr>

  <tr>

   <td width="144">read(x)</td>

   <td width="144">read(y)</td>

   <td width="125">read(z)</td>

  </tr>

  <tr>

   <td width="144">write(y,x+1)</td>

   <td width="144">write(x,y+1)</td>

   <td width="125">write(x,z+1)</td>

  </tr>

  <tr>

   <td width="144">commit</td>

   <td width="144">commit</td>

   <td width="125">write(y,z+2)</td>

  </tr>

  <tr>

   <td width="144"> </td>

   <td width="144"> </td>

   <td width="125">commit</td>

  </tr>

 </tbody>

</table>




Assume that the initial values of the persistent data items x, y, and z are the following. x = 1, y = 2, and z= 3.

Show a sample concurrent execution of the transactions T1, T2, and T3 that is <u>nonconflict serializable</u> and that is <u>view serializable</u>.

Prove, that the execution is <u>nonconflict serializable</u> and that it is <u>view serializable</u>.

When visualizing the concurrent executions use a technique of two-dimensional diagrams presented to you during the lecture classes, for example, see a presentation 10 Introduction to Transaction Processing (1), slide 9.

Show a sample concurrent execution of the transactions T1, T2, and T3 that is <u>conflict</u> <u>serializable</u> and that is <u>not order-preserving conflict serializable</u>.

Prove, that the execution is <u>conflict serializable</u> and that it is <u>not order-preserving</u> <u>conflict serializable</u>.

When visualizing the concurrent executions use a technique of two-dimensional diagrams presented to you during the lecture classes, for example, see a presentation 10 Introduction to Transaction Processing (1), slide 9.

Show a sample concurrent execution of the transactions T1, T2, and T3 that is <u>recoverable</u> and that is <u>not strict</u>.

Prove, that the execution is <u>recoverable</u> and that it is <u>not strict</u>.

When visualizing the concurrent executions use a technique of two-dimensional diagrams presented to you during the lecture classes, for example, see a presentation 10 Introduction to Transaction Processing (1), slide 9.

Deliverables

A file solution1.pdf with:

<ul>

 <li>a visualization of a sample concurrent execution of the transactions T1, T2, and T3 that is <u>nonconflict serializable</u> and that is <u>view serializable</u> and a proof that the execution is <u>nonconflict serializable</u> and that it is <u>view serializable</u>.</li>

 <li>visualization of a sample concurrent execution of the transactions T1, T2, and T3 that is <u>conflict serializable</u> and that is <u>not order-preserving conflict serializable</u> and a proof that the execution is <u>conflict serializable</u> and that it is <u>not order-preserving</u> <u>conflict serializable</u>.</li>

 <li>visualization of a sample concurrent execution of the transactions T1, T2, and T3 that is <u>recoverable</u> and that is <u>not strict</u> and a proof that the execution is <u>recoverable</u> and that it is <u>not strict</u>.</li>

</ul>

<u>                                                                                                                                                            </u>

<h2>Task 2 (6 Serialization graph testing, 2PL, and Timestamp ordering scheduler</h2>

Consider a concurrent execution of database transactions T1, T2, and T3 such that the execution is not controlled by any scheduler.

<u>T1       T2       T3  </u> read(x)

write(x,x+1)

read(y)            write(x,y+1)

read(z)

write(x,z+1)

read(z) write(z,x+2)

Assume, that the transactions attempt to interleave their operations in the same way as in the execution above. Show a sample concurrent execution of the transactions T1, T2, and T3 that is controlled by <u>serialization graph testing scheduler</u>.

Draw a <u>conflict serialization graph</u>.

When visualizing the concurrent executions use a technique of two-dimensional diagrams presented to you during the lecture classes, for example, see a presentation 10 Introduction to Transaction Processing (1), slide 9.

Assume, that the transactions attempt to interleave their operations in the same way as in the execution above. Show a sample concurrent execution of the transactions T1, T2, and T3 that is controlled by <u>2PL scheduler</u>.

Assume, that to simplify the problem we use only a general concept of a lock and we do not distinguish between shared locks and exclusive locks.

When visualizing the concurrent executions use a technique of two-dimensional diagrams presented to you during the lecture classes, for example, see a presentation 10 Introduction to Transaction Processing (1), slide 9.

Assume, that the transactions attempt to interleave their operations in the same way as in the execution above. Show a sample concurrent execution of the transactions T1, T2, and T3 that is controlled by <u>timestamp ordering scheduler</u>.

When visualizing the concurrent executions use a technique of two-dimensional diagrams presented to you during the lecture classes, for example, see a presentation 10 Introduction to Transaction Processing (1), slide 9.

Show the data items accessed by the transactions together with the timestamps left by the transactions on the data items.

<h2>Deliverables</h2>

A file solution2.pdf with:

<ul>

 <li>visualization of a sample concurrent execution of the transactions T1, T2, and T3 that is controlled by <u>serialization graph testing scheduler</u> and a conflict serialization graph,</li>

</ul>




<ul>

 <li>visualization of a sample concurrent execution of the transactions T1, T2, and T3 that is controlled by <u>2PL scheduler</u>,</li>

</ul>




<ul>

 <li>visualization of a sample concurrent execution of the transactions T1, T2, and T3 that is controlled by <u>timestamp ordering scheduler</u>.<strong>   </strong></li>

</ul>

<h2>Task 3 (6 Processing transactions at READ COMMITTED level by a snapshot isolation scheduler</h2>

Consider a stored PL/SQL function MAX_MIN given below.

CREATE OR REPLACE FUNCTION MAX_MIN ( orderkey IN NUMBER )

RETURN NUMBER IS  max_value NUMBER(12);  min_value NUMBER(12);

BEGIN

SELECT MAX(L_QUANTITY * L_EXTENDEDPRICE)

INTO max_value

FROM LINEITEM

WHERE L_ORDERKEY = orderkey;

SELECT MIN(L_QUANTITY * L_EXTENDEDPRICE)

INTO min_value

FROM LINEITEM

WHERE L_ORDERKEY = orderkey;




RETURN max_value-min_value;

END MAX_MIN;

/

Show a sample concurrent execution of the function at READ COMMITTED level that interleaves the operations with another transaction and such that a result returned by the function is incorrect. The operations performed by another transaction are up to you.

When visualizing the concurrent executions use a technique of two-dimensional diagrams presented to you during the lecture classes, for example, see a presentation 14 Transaction Processing in Oracle DBMS slide 16.

Rewrite a stored function such that it can be processed at READ COMMITTED level and show how the improved function interleaves the operations with another transaction and such that a result returned by the function is always correct.

When visualizing the concurrent executions use a technique of two-dimensional diagrams presented to you during the lecture classes, for example, see a presentation 14 Transaction Processing in Oracle DBMS slide 16.

<h2>Deliverables</h2>

A file solution3.pdf with:

<ul>

 <li>visualization of a sample concurrent execution of the function at READ COMMITTED level that interleaves the operations with another transaction and such that a result returned by the function is incorrect,</li>

</ul>




<ul>

 <li>visualization of a sample concurrent execution of an improved function at READ COMMITTED level that interleaves the operations with another transaction and such that a result returned by the function is always correct.</li>

</ul>

<h2>Task 4 (2 Deadlocks</h2>

Consider a stored PL/SQL function SWAP given below.




CREATE OR REPLACE PROCEDURE SWAP( order_key1  IN NUMBER,                                   order_key2  In NUMBER ) IS




total_price1 ORDERS.O_TOTALPRICE%TYPE;  total_price2 ORDERS.O_TOTALPRICE%TYPE;




BEGIN

SELECT O_TOTALPRICE

INTO total_price1

FROM ORDERS

WHERE O_ORDERKEY = order_key1;




SELECT O_TOTALPRICE

INTO total_price2

FROM ORDERS

WHERE O_ORDERKEY = order_key2;




UPDATE ORDERS

SET O_TOTALPRICE = total_price1

WHERE O_ORDERKEY = order_key2;




UPDATE ORDERS

SET O_TOTALPRICE = total_price2

WHERE O_ORDERKEY = order_key1;




END SWAP;

/




Show a sample concurrent execution of two transactions both processing a function SWAP, both running at READ COMMITTED level, and such that the execution leads to a deadlock.




When visualizing the concurrent executions use a technique of two-dimensional diagrams presented to you during the lecture classes, for example, see a presentation 14 Transaction Processing in Oracle DBMS slide 16.




<h2>Deliverables</h2>

A file solution4.pdf with visualization of a sample concurrent execution of two transactions both processing a function SWAP, both running at READ COMMITTED level, and such that the execution leads to a deadlock.

<u>                                                                                                                                                </u>


