### blade
---
https://github.com/lets-blade/blade

```java
public static void main(String[] args) {
  Blabe.of().get("/", ctx -> ctx.text("Hello Blade")).start();
}

public static void main(String[] args) {
  Blade.of()
    .get("/users/21", getting)
    .post("/save", posting)
    .delete("/remove", deleting)
    .put("/putValue", putting)
    .start();
}

@Path
public class IndexController {
  @GetRoute("signin")
  public String signin() {
    return "sigin.html";
  }
  
  @PostRoute("signin")
  @JSON
  public RestResponse doSignin(RouteContext ctx) {
    return RestResponse.ok();
  }
}

public static void main(String[] args) {
  Blade.of().get("/user", ctx -> {
    Integer age = ctx.fromInt("age");
    System.out.println("age is:" + age);
  }).start();
}

@PostRoute("/save")
public void savePerson(@Param String username, @Param Integer age) {
  System.out.println("username is:" + username + ", age is:" + age)
}

public static void main(String[] args) {
  Blade blade = Blade.of();
  
  blade.get("/user/:uid", ctx -> {
    Integer uid = ctx.pathInt("uid");
    ctx.text("uid : " + uid);
  });
  
  blade.get("/users/:uid/post/:pid", ctx -> {
    Integer uid = ctx.pathInt("uid");
    Integer pid = ctx.pathInt("pid");
    String msg = "uid = " + uid + ", pid = " + pid;
    ctx.text(msg);
  });
  
  blade.start();
}

public static void main(String[] args) {
  Blade.of().post("/body", ctx -> {
    System.out.println("body string is:" + ctx.bodyToString())
  });
}


public class User {
  private String username;
  private Integer age;
}

@PostRoute("/users")
public void saveUser(@Param User user) {
  System.out.println("user => " + user);
}

@PostRoute("/users")
public void saveUser(@Param(name="u") User user) {
  System.out.println("user => " + user);
}


@Bean
public class GlobalExceptionHandler extends DefaultsExceptionHandler {
  @Override
  public void handle(Exception e) {
    if (e instanceof CustomException) {
      CustomException customException = (CustomException) e;
      String code = customException.getCode();
    } else {
      super.handle(e);
    }
  }
}

Blade.of().listen(9001).start();

public static void main(String[] args) {
  Blade.of().use(new BasicAuthMiddleware()).start();
}
```

```sh
http.auth.username=admin
http.auth.password=12345
server.port=9001
java -jar blade-app.jar --server.port=9001
server.ssl.enable=true
server.ssl.cert-path=cert.pem
server.ssl.private-key-path=private_key.pem
server.ssl.private-key-pass=123456

curl -X GET http://127.0.0.1:9000/users/biezhi/2
curl -X POST http://127.0.0.1:9000/body -d '{"username":"biezhi","age":22}'
```

```
```


