# Java7 Features 
#### 1- Catch Multiple Exceptions 
Consider the following example, which contains duplicate code in each of the catch blocks:
```java
catch (IOException ex) {
     logger.log(ex);
     throw ex;
catch (SQLException ex) {
     logger.log(ex);
     throw ex;
}
```
The following example, which is valid in Java SE 7 and later, eliminates the duplicated code:
```java
catch (IOException|SQLException ex) {
    logger.log(ex);
    throw ex;
}
```