# [Apollo-Android, GraphQL] Android 프로젝트에 Apollo-Android 추가하기



### Apollo-Android: https://github.com/apollographql/apollo-android

위 사이트에서 "**Adding Apollo-Android to your Project**" 부분을 참고 하였습니다.



## 1. project의 root build.gradle 파일에 다음 코드를 삽입

```
buildscript {
  repositories {
    jcenter()
  }
  dependencies {
    classpath("com.apollographql.apollo:apollo-gradle-plugin:x.y.z")
  }
}
```

위 코드에서 x.y.z에 들어갈 숫자는https://github.com/apollographql/apollo-android 사이트에서 "Adding Apollo-Android to you Project" 부분의 "The latest Gradle plugin version"을 참고하면 된다. 

![The latest Gradle plugin version](images/image1.png)

>  2019.12.10 기준 1.2.2



## 2. 그 후 app의 build.gradle 파일에 다음 코드를 삽입

```
apply plugin: 'com.apollographql.android'

repositories {
    jcenter()
}

dependencies {
  implementation("com.apollographql.apollo:apollo-runtime:x.y.z")
  
  // If not already on your classpath, you might need the jetbrains annotations
  compileOnly("org.jetbrains:annotations:13.0")
  testCompileOnly("org.jetbrains:annotations:13.0")
}
```

여기서도 `implementation("com.apollographql.apollo:apollo-runtime:x.y.z")` 부분에서 x.y.z에 latest gradle file version을 넣어주면 된다.



**NOTE: Apollo Gradle plugin을 사용하기 위해서는 Gradle 버전이 5.1.1 이상이어야 한다.**
