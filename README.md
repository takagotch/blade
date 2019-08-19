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













```

```
```

```
```


