### With Spring Boot

Spring과 QueryDsl을 같이 사용하려면 사전에 해야하는 설정이 꽤 많다.

### 사전 설정

Gradle에 다음과 같은 설정을 한다.

1. Plugin 추가

```gradle
    plugins {
        id "com.ewerk.gradle.plugins.querydsl" version "1.0.10"
    }
```

2. dependencies 추가

```gradle
    dependencies {
        implementation "com.querydsl:querydsl-jpa:${queryDslVersion}"
	    implementation "com.querydsl:querydsl-apt:${queryDslVersion}"
    }
```

3. def 추가

```gradle
    def querydslDir = "$buildDir/generated/querydsl"
```

4. querydsl 추가

```gradle
    querydsl {
	jpa = true
	querydslSourcesDir = querydslDir
}
```

5. sorceSets 추가

```gradle
    sourceSets {
	    main.java.srcDir querydslDir
    }
```

6. compileQuerydsl 추가

```gradle
    compileQuerydsl {
        options.annotationProcessorPath = configurations.querydsl
    }
```

7. configurations 추가

```gradle
    configurations {
        compileOnly {
            extendsFrom annotationProcessor
        }
        querydsl.extendsFrom compileClasspath
    }
```

8. buildscript 추가

```gradle
    buildscript {
        ext {
            queryDslVersion = "5.0.0"
        }
    }
```

9.  Gradle reload

차근차근 하다보면 된다. (아마도)
