# 👾 Unit Test

## Introduction

AppFlowy is becoming a complex application, in order to maintain stability, we encourage developers to write more tests. Testing your code ensures that the software you develop works as expected and makes it less vulnerable to attackers.

This article will cover:

* The tests in AppFlowy
* How to run the tests in AppFlowy
* How to write a test in AppFlowy
* Code coverage

## The tests in AppFlowy

AppFlowy is written in Dart and Rust. We call it `frontend` tests in `Dart` and `Backend` tests in `Rust`.

### frontend tests

The frontend tests locate in `frontend/app_flowy/test.` It contains three folders. The bloc test folder, integration test folder, and widget test folder.

| bloc test        | It contains the [bloc test](https://pub.dev/packages/bloc\_test)s of AppFlowy.                                      |
| ---------------- | ------------------------------------------------------------------------------------------------------------------- |
| widget test      | It contains the [widget test](https://docs.flutter.dev/cookbook/testing/widget/introduction)s of AppFlowy.          |
| integration test | It contains the [integration test](https://docs.flutter.dev/cookbook/testing/integration/introduction)s of AppFlowy |

When creating a new test, you should put it in the right folder.

### Backend tests

WIP

## How to run the tests

#### Run tests one by one

In order to run the tests one by one, it needs to build the Backend library first.

```bash
// Make sure your current path is AppFlowy/frontend
cargo make build-test-lib
```

After building the Backend library, you can click the `Run|Debug` button to run the test.

<figure><img src="../../../../.gitbook/assets/image (2) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Run all the tests

```shell
// Make sure your current path is AppFlowy/frontend
cargo make dart_unit_test
```

## How to write a test

WIP

## Code coverage

WIP
