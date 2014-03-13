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

- Description of the project
   JSBML uses the concept of abstract syntax trees to work with mathematical expressions. At the moment, all different kinds of formulas are implemented in one complex class,ASTNode.It has a nested enumeration with 64 different types and many methods to deal with these types.This is not very efficient and straightforward.For example,every time compiling a ASTNode to ASTNodeValue,it will go through a long period case jugement(64 in the worst situation).As konwn,in cpu's perspect,a lot of jumps are very time consuming.So it is necessary to redesign this complex class.

- Timeline

#### Week1(5.19-5.25)
    - Set up code repos and blog
    - Download JSBML source code and import to Eclipse
    - Read SBML papers and JSBML source code to get deeper understanding

#### Week2(5.26-6.1)
    - Redesign ASTNode as a abstract class and implement some common methods 
    - Classify all the 64 types into 6 group:number,operator,name of identifier,constant,basic function and logical and relational function
    - Design 6 abstract classes for these groups
    - Implement the common methods within each group 

#### Week3 (6.2-6.8)
    - 
