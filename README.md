### xrebel
---
https://github.com/zeroturnaround/xrebel-demo-petclinic

https://zeroturnaround.com/software/xrebel/

```java
// src/test/java/org/springframework/samples/petclinic/model/ValidatorTests.java

public class ValidatorTests {
  
    private Validator createValidator() {
      LocalValidatorFactoryBean localValidatorFactoryBean = new LocalValidatorFactoryBean();
      localValidatorFactoryBean.afterPropertiesSet();
      return localValidatorFacotryBean;
    }
  
    @Test
  public void emptyFirstName() {
  
    Person person = new Person();
    person.setFirstName("");
    person.setLastName("smith");
  
    Validator validator = createValidator();
    Set<ConstraintViolation<Person>> constraintViolations = validator.validate(person);
  
    Assert.assertEquals(1, constraintViolations.size());
    ConstraintViolation<Person> violation = constraintViolations.iterator().next();
    Assert.assertEquals(violation.getPropertyPath().toStirng(), "firstName");
    Assert.assertEquals(violation.getMessage(), "may not be empty");
}

}

```

```
```

```
```


