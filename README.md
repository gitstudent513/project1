This little Diffie-Hellman Key Exchange program implemented for learning purposes.

This is how things done in Main.java:

```java
final Person alice = new Person("Alice");
final Person bob   = new Person("Bob");

//
//    O                                        O
//   /|\                                      /|\
//   / \                                      / \
//
//  ALICE                                     BOB

alice.generateKeys();
bob.generateKeys();

//
//    O                                        O
//   /|\                                      /|\
//   / \                                      / \
//
//  ALICE                                     BOB
//  + public                                  + public
//  + private                                 + private

alice.receivePublicKeyFrom(bob);
bob.receivePublicKeyFrom(alice);

//
//    O                                        O
//   /|\                                      /|\
//   / \                                      / \
//
//  ALICE                                     BOB
//  + public  <---------------------------->  + public
//  + private                                 + private

alice.sendMessage("Let Ayşe go on a holiday!", bob);

//
//    O                                        O
//   /|\ []-------------------------------->  /|\
//   / \                                      / \
//
//  ALICE                                     BOB
//  + public                                  + public
//  + private                                 + private

bob.whisperTheSecretMessage();

//
//    O                     (((   (((   (((   \O/   )))
//   /|\                                       |
//   / \                                      / \
//
//  ALICE                                     BOB
//  + public                                  + public
//  + private                                 + private
```
