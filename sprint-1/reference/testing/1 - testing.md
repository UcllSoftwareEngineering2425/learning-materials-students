# Spring Testing

Start by checking out the Testing slide-deck on Toledo.

You'll have to figure out how to make the tests yourselves, but here
are some key words to get you started on your search:

- `@SpringBootTest`
- `@WebMvcTest`
- `@DataJpaTest`
- `MockMvc` / `@WebTestClient`
- `@MockBean`

## Integration tests and end to end tests

Here are some useful sources about integration tests with Spring:

- [Spring Boot Integration Testing With @SpringBootTest](https://www.arhohuttunen.com/spring-boot-integration-testing/)
- [Testing the Web Layer](https://spring.io/guides/gs/testing-web)
- [Testing with Spring Boot and @SpringBootTest](https://reflectoring.io/spring-boot-test/)
- [Practical Test Pyramid](https://martinfowler.com/articles/practical-test-pyramid.html)

## Tests with Spring Security

When you're writing end-to-end or HTTP integration tests you may
run into 401/403 errors. You can either use `@WithMockUser` or
use the `JwtService` to generate JSON Web Tokens and provide the
appropriate `Authorization` header when performing your request.

Here are some useful sources to help you on your way:

- [Testing Method Security](https://docs.spring.io/spring-security/reference/servlet/test/method.html)
- [Spring Security for Spring Boot Integration Tests](https://www.baeldung.com/spring-security-integration-tests)