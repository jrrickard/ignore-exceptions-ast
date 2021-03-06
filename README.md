[![Build Status](https://travis-ci.org/danveloper/ignore-exceptions-ast.svg?branch=master)](https://travis-ci.org/danveloper/ignore-exceptions-ast)
[![Coverage Status](https://coveralls.io/repos/github/danveloper/ignore-exceptions-ast/badge.png?branch=master)](https://coveralls.io/github/danveloper/ignore-exceptions-ast?branch=master)
[![Download](https://api.bintray.com/packages/danveloper/maven/ignore-exceptions-ast/images/download.svg)](https://bintray.com/danveloper/maven/ignore-exceptions-ast/_latestVersion)


[![forthebadge](http://forthebadge.com/images/badges/fuck-it-ship-it.svg)](http://forthebadge.com) [![forthebadge](http://forthebadge.com/images/badges/reading-6th-grade-level.svg)](http://forthebadge.com)
[![forthebadge](http://forthebadge.com/images/badges/makes-people-smile.svg)](http://forthebadge.com)

Ignore Exceptions Groovy AST Transformation
---

This provides a local AST transform to ignore all exceptions thrown from a method.

Usage
---

Add the artifact to your build:

```groovy
repositories {
  jcenter()
}

dependencies {
  compile 'com.github.danveloper.ast:ignore-exceptions-ast:1.0.0-rc-2'
}
```

```groovy
package app

import com.github.danveloper.ast.IgnoreExceptions

class Main {

  @IgnoreExceptions // <1>
  public static void main(String[] args) {
    throw new RuntimeException() // <2>
  }
}
```

 1. Annotate your method with `@IgnoreExceptions`.
 2. Have your method throw an exception.

Run the code and notice that no exception is thrown!

Likewise, you can use the `@Pokemon` annotation (gotta catch 'em all):

```groovy
package app

import com.github.danveloper.ast.Pokemon

class Main {

  @Pokemon
  public static void main(String[] args) {
    throw new RuntimeException()
  }
}
```

License
---

STEAL THIS CODE PL™

Author
---

https://twitter.com/danveloper[@danveloper]
