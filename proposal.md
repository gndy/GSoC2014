# Redesignment of the mathmatical classes

### Personal Information

- **Name**: Lei Wen 
- **Email**: gndy90@gmail.com
- **University**: Wuhan Institute of Virology, University of Chinese Academy of Sciences
- **Current Enrollment**: Second-year Master Student in Bioinformatics
- **Biography**: 
    - 2008-2012: Bachelor of Science in Biology Science, Hebei University, Baoding, China;
    - 2012-2014: Master of Science in Bioinformatics, University of Chinese Academy of Sciences, Beijing, China.

---------------------------------------
### Programming Experience

- **Java**:about 3 years **Android**:1 year
    - **SnoreHunter**(http://github.com/gndy/SnoreHunter) An Android app to record snore in sleep.It can calculate the total and seperate snore time,andrecord the begin time of each snore period.When users listen to the record,they can just jump to each snore begin timepoint without going through the whole record.I got a recognition award in the programming contest hold by the National Science Library, Chinese Academy of Sciences (NSLC)(http://www.openinnovation.cn/node/10523) .

- **Python**: 1 year
    - Some Python scripts for my research.(http://github.com/gndy/PythonCode ).

- I also wrote some small Java program for my classmates.(http://github.com/gndy?tab=repositories ).

-----------------------------------------

### Goals for GSoC

My interests are phylogenetics and Next-Generation Sequencing(NGS).Now I am working on the drug resistance of HBV based on Ultra-deep Pyrosequencing(UDPS) data.I have wrote many Java programs for my research,but never designed a whole package in a library.I think it is nice to have such kind of experience.

-------------------------------------------

### Summer Plan

I dont't have plans in summer that conflict with GSoC.So I have enough time to work and focus on the project.

-------------------------------

### Ideas for the Project 
JSBML uses the concept of abstract syntax trees to work with mathematical expressions. At the moment, all different kinds of formulas are implemented in one complex class,ASTNode.It has a nested enumeration with 64 different types and many methods to deal with these types.This is not very efficient and straightforward.For example,every time compiling a ASTNode to ASTNodeValue,it might go through a long period type matching(64 at worst).As known,conditional jumps are very time consuming from CPU's perspective.So it is necessary to redesign this complex class.In redesignment, ASTNode class could be kept as a facade to expose the same interface for compatibility.All the methods in ASTNode are implemented by a serials of well organized small classes which are also base on TreeNode structure.Redesignment is based on the Facade and Composite pattern.

### Timeline

#### Week1 (5.19-5.25)
- Set up code repos and blog
- Download JSBML source code and import to Eclipse
- Read SBML papers and JSBML source code to get deeper understanding

#### Week2 (5.26-6.1)
- Modify the ASTNode to a facade
- Classify all the 64 types into 6 group:number,operator,name of identifier,constant,basic function and logical and relational function
- Design 6 abstract classes for these groups
- Implement the common methods within each group 

#### Week3 (6.2-6.8)
- Design classes representing numbers:REAL,INTEGER.  
- Design classes representing constants:PI,E,TRUE,FALSE,AVOGADRO and REAL_E.
- Test with ASTNode class

#### Week4 (6.9-6.15)
- Design classes representing operators
- Including POWER,PLUS,MINUS,TIMES,DIVIDE,RATIONAL,NAME_TIME and FUNCTION_DELAY.
- Test with ASTNode class

#### Week5 (6.16-6.22)
- Design classes representing names of identifiers:PARAMETERS, FUNCTIONS, SPECIES etc.
- Test with ASTNode class

#### Week6(6.23-6.29)
- Design classes representing logical and relational functions
- Logical: AND,OR,NOT,XOR 
- Relational:EQ,NEQ,GEQ,LEQ,LT,GT
- Test with ASTNode class

#### Week7-Week9 (6.30-7.20)
- Design classes representing basic-functions
- 36 functions in total
- Test with ASTNode class

#### Week10-Week11 (7.21-8.3)
- Integrate all the classes
- Overall test and debug

#### Week12-Week13 (8.4-8.18)
- cleanup existing code,complete the comments
- Write documentation and tutorial for this package
- Submit everything to Google
