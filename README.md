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
- Small!! : 함수의 첫 번째 규칙은 그것들이 작아야한다는 것입니다. extract method.
- Do One Thing : Function은 한가지 일만 해야한다
- switch ~ case 문은  ABSTRACT FACTORY 기반으로 변경할 수 있다
- 함수의 argument 는 3개 이상 피해라. 인수가 많으면 테스트도 많아진다   함수가 두 개 또는 세 개의 인수를 필요로 할 때, 이러한 인수 중 일부는 자체 클래스로 래핑되어야합니다.
```
// bad
Circle makeCircle(double x, double y, double radius); 
// good
Circle makeCircle(Point center, double radius);
public String format(String format, Object... args)
void monad(Integer... args);
void dyad(String name, Integer... args);
void triad(String name, int count, Integer... args);

```
- Command Query Separation
```
// bad
if (set("username", "unclebob"))...
 
// good
if (attributeExists("username")) { 
    setAttribute("username", "unclebob"); ...
}
```
- 에러코드를 리턴하는대신 Excpetion을 던지는것이 더 낮다
```
if (deletePage(page) == E_OK) {
    if (registry.deleteReference(page.name) == E_OK) {
        if (configKeys.deleteKey(page.name.makeKey()) == E_OK){ 
            logger.log("page deleted");
        } 
        else {
            logger.log("configKey not deleted");
        }
       } 
       else {
        logger.log("deleteReference from registry failed"); }
    } else {
        logger.log("delete failed"); return E_ERROR;
}

// good
try {
    deletePage(page); 
    registry.deleteReference(page.name); 
    configKeys.deleteKey(page.name.makeKey());
}
catch (Exception e) {
    logger.log(e.getMessage());
}

```
- Don’t Repeat Yourself