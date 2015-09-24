# Dart Custom Testing Framework
A testing framework that runs in the Dartium browser and is compatible with the Webstorm IDE.

## Motivation
The Webstorm IDE crashes with Dart's test library, and the simples solution 
has been to write an alternative framework.

## Sample Usage

```dart
import './dartTest/dartTest.dart';

class Sky {
  static bool get isBlue => true;
}

class Dog {
  static bool get isMansBestFriend => true;
}

class Cat {
  static num get numLives => 9;
}

main() {
  new Module('Sample Usage', [
    new Group('Test Group A:', [
      new Test('The sky is blue', () {
        expect.isTrue(Sky.isBlue);
      }),
      new Test('Yes means no', () {
        expect.areEqual('yes', 'no');
      }),
      new Test('A dog is a man\'s best friend', () {
        expect.isTrue(Dog.isMansBestFriend);
      }),
    ]),
    new Group('Test Group B:', [
      new Test('A cat has nine lives', () {
        expect.areEqual(Cat.numLives, 9);
      }),
      new Test('My cat is a dog', () {
        var myCat = new Cat();
        expect.isTrue(myCat is Dog);
      }),
    ])
  ]);
}

```
## Sample Output

![Alt text](/sampleOutput.png?raw=true)

## Contributors

Ian McCall