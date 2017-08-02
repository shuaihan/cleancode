# Meaningful Names
- variables, our functions, our arguments, classes, and packages 명을 의도가 보이도록 명확히 해라
```
// bad
int d; // elapsed time in days
// good
int elapsedTimeInDays; 
int daysSinceCreation; 
int daysSinceModification; 
int fileAgeInDays; 
```
- Classes and objects should have noun or noun phrase names 
- Methods should have verb or verb phrase names 
- 생성자보다 의미있는 이름을 갖는 static factory methods 가 낮다
```
// 
Complex fulcrumPoint = Complex.FromRealNumber(23.0);
// better
Complex fulcrumPoint = new Complex(23.0);
```
- 클래스마다 같은 동작인데 다른 method name 을 갖는것은 나쁘다 ( ex. fetchm retrieve, get...)
- 두 개의 다른 아이디어에 대해 동일한 용어를 사용하는 것은 본질적으로 말장난입니다. (ex, add, append, insert 는 다 다르다)
- 코드를 읽는 사람들은 프로그래머가 될 것임을 기억하십시오. 따라서 컴퓨터 과학 (CS) 용어, 알고리즘 이름, 패턴 이름, 수학 용어 등을 사용 (ex )AccountVisitor , JobQueue
    
# Functions
    