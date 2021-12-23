# Clean Code 
## 1- Start Clearing Up 
#### 1- Avoid Unnecessary Comparisons

<table>
<tr>
<th>
Before 
</th>
<th>
After
</th>
</tr>

<tr>
<td>
  
```java
class Laboratory {
   Microscope microscope;
  
   Result analyze(Sample sample) {
      if (microscope.isInorganic(sample) == true) {
         return Result.INORGANIC; 
      } else {
         return analyzeOrganic(sample); 
      }
   }
  
   private Result analyzeOrganic(Sample sample) { 
     if (microscope.isHumanoid(sample) == false) {
       return Result.ALIEN; 
     } else {
       return Result.HUMANOID; 
     }
   } 
}
```
  </td>
  <td>
    
```java
class Laboratory {
   Microscope microscope;
  
   Result analyze(Sample sample) {
      if (microscope.isInorganic(sample)) {
         return Result.INORGANIC; 
      } else {
         return analyzeOrganic(sample); 
      }
   }
  
   private Result analyzeOrganic(Sample sample) { 
     if (!microscope.isHumanoid(sample)) {
       return Result.ALIEN; 
     } else {
       return Result.HUMANOID; 
     }
   } 
}
```
  </td>
  </tr>
  </table>
