# Redesign the implementation of mathematical formulas in JSBML

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
    - **SnoreHunter**(http://github.com/gndy/SnoreHunter) An Android app to record snore in sleep.It can calculate the total and seperate snore time,andrecord the begin time of each snore period.When users listen to the record,they can just jump to each snore begin timepoint without going through the whole record.I got a recognition award in the programming contest hold by the National Science Library, Chinese Academy of Sciences (NSLC)(http://www.openinnovation.cn/node/10523 ).

- **Python**: 1 year
    - Some Python scripts for my research.(http://github.com/gndy/PythonCode ).

- I also wrote some small Java program for my classmates.(http://github.com/gndy?tab=repositories ).

-----------------------------------------

### Goals for GSoC

My interests are phylogenetics and Next-Generation Sequencing(NGS).Now I am working on the drug resistance of HBV based on Ultra-deep Pyrosequencing(UDPS) data.I have wrote many Java programs for my research,but never designed a whole package in a library.I think it is cool to engage in GSoC and will be a nice experience.

-------------------------------------------

### Summer Plan

I dont't have plans that conflict with GSoC in summer.So I have enough time to work on the project.

-------------------------------

### Ideas for the Project 
JSBML uses the concept of abstract syntax trees to work with mathematical expressions. At the moment, all different kinds of formulas are implemented in one complex class,ASTNode.It has a nested enumeration which contains 64 different types and many methods to deal with these types.This is not very efficient and straightforward.For example,every time compiling a ASTNode to ASTNodeValue,it might go through a long period type matching(64 at worst).As known,conditional jumps are very time consuming from CPU's perspective.So it is necessary to redesign this complex class.In redesignment, ASTNode class could be kept as a facade to expose the same interface for compatibility.All the methods in ASTNode are implemented by a serials of well organized small classes which are also base on TreeNode structure.Redesignment is according to the Facade and Composite pattern.

### Timeline

#### Week1 (5.19-5.25) preparation
- Set up code repos and blog.
- Download JSBML source code and import to Eclipse.
- Read SBML papers and JSBML source code to get deeper a understanding.
- **Difficulty**:easy.

#### Week2 (5.26-6.1) overall design
- Keep the old ASTNode class as a facade and implement some basic methods.
- Classify all the 64 types into 6 groups:number,operator,name of identifier,constant,basic function and logical and relational function.
- Design 6 abstract classes for these groups.
- Implement the basic methods of each abstract class.
- **Difficulty**:hard.The ASTNode is a very complex class with a lot of fields and methods.How to make it become a facade and coordinate with all the small classes is challenging.

#### Week3 (6.2-6.8) numbers and constants
- Design classes for numbers:REAL,INTEGER.  
- Design classes for constants:PI,E,TRUE,FALSE,AVOGADRO and REAL_E.
- Implement the related part in ASTNode and Test. 
- **Difficulty**:easy.These types are simple and easy to understand.

#### Week4 (6.9-6.15) operators
- Design classes for operators
- Including POWER,PLUS,MINUS,TIMES,DIVIDE,RATIONAL,NAME_TIME and FUNCTION_DELAY.
- Implement the related part in ASTNode and Test. 
- **Difficulty**:easy.

#### Week5 (6.16-6.22) names of identifiers
- Design classes for names of idetifiers:PARAMETERS, FUNCTIONS, SPECIES etc.
- Implement the related part in ASTNode and Test.
- **Difficulty**:medium.These types are from SBML model,need to refer the SBML papers.

#### Week6(6.23-6.29) logical and relational functions
- Design classes for logical and relational functions.
- Logical: AND,OR,NOT,XOR.
- Relational:EQ,NEQ,GEQ,LEQ,LT,GT.
- Implement the related part in ASTNode and Test.
- **Difficulty**:easy.

#### Week7 (6.30-7.6) part 1 of 36 basic functions
- Design classes for basic-functions.
- Most of them are trigonometric functions.
- Implement the related part in ASTNode and Test.
- **Difficulty**:easy.

#### Week8 (7.7-7.13) part 2 of 36 basic functions
- Continue designing classes for basic-functions.
- Implement the related part in ASTNode and Test.
- **Difficulty**:easy.

#### Week9 (7.14-7.20) part 3 of 36 basic functions
- Continue designing classes for basic-functions.
- Implement the related part in ASTNode and Test.
- **Difficulty**:easy.

#### Week10 (7.21-7.27) integration and test
- Integrate all the classes.
- Overall test and debug.
- **Difficulty**:medium to hard.Overall test and debug will be hard because of the complex structure of ASTNode.

#### Week11 (7.28-8.3) test and debug
- Still test and debug.

#### Week12 (8.4-8.10) clean up 
- Cleanup existing code.
- Complete the comments.

#### Week13 (8.11-8.18) documentation and tutorial
- Write documentation and tutorial for this package
- Submit everything needed. 
