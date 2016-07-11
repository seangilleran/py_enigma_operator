# Enigma Operator

Wrapper for py-enigma encode/decode. Also provides tools for creating key sheets and code books. For more info and for documentation, see py-enigma, here: https://bitbucket.org/bgneal/enigma/

### Install
```python
pip install py-enigma-operator
```

### Usage

Messages are encoded along with their encrypted message keys and with their transmitting operator's random _grundstellung_. Both transmitter and reciever must have the same code book, and the reciever must know on what day the message was encoded. (Assuming, of course, the reciever does not have access to a Bombe!)

```python
e = EnigmaOperator('/path/to/key/sheet/file')
plaintext = 'THEXRUSSIANSXAREXCOMINGX'
ciphertext = e.encrypt(plaintext)
```

```python
e = EnigmaOperator('/path/to/key/sheet/file')
ciphertext = 'XIWIJXIJWOZLCKFMEMNGNEIAIJLBO'
plaintext = e.decrypt(ciphertext)
```

You can also use ```EnigmaOperator``` to generate a code book. Once you do, make sure all of your recievers have a copy!

```python
EnigmaOperator.random_codebuch('path/to/key/sheet/file')
```

Have fun!
