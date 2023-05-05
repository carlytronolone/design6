# Lab 10 - Blockchain
## Files for Lab 10 will be stored here
# Procedure
## Given commands:
```
$ cd ~/iot/lesson10
$ cat hash_value.py
$ python3 hash_value.py
$ python3 hash_value.py
```
## Results:
```
carly@MSI MINGW32 ~/iot/lesson10 (master)
$ cat hash_value.py
"""
https://docs.python.org/3/using/cmdline.html#envvar-PYTHONHASHSEED
If PYTHONHASHSEED is not set or set to random, a random value is used to to seed the hashes of str and bytes objects.
If PYTHONHASHSEED is set to an integer value, it is used as a fixed seed for generating the hash() of the types covered by the hash randomization.
Its purpose is to allow repeatable hashing, such as for selftests for the interpreter itself, or to allow a cluster of python processes to share hash values.
The integer must be a decimal number in the range [0,4294967295]. Specifying the value 0 will disable hash randomization.

https://www.programiz.com/python-programming/methods/built-in/hash
hash(object) returns the hash value of the object (if it has one). Hash values are integers.
They are used to quickly compare dictionary keys during a dictionary lookup.
Numeric values that compare equal have the same hash value even if they are of different types, as is the case for 1 and 1.0.
For objects with custom __hash__() methods, note that hash() truncates the return value based on the bit width of the host machine.
"""

# hash for integer unchanged
print('The hash for 1 is:', hash(1))

# hash for decimal
print('The hash for 1.0 is:',hash(1.0))
print('The hash for 3.14 is:',hash(3.14))

# hash for string
print('The hash for Python is:', hash('Python'))

# hash for a tuple of vowels
vowels = ('a', 'e', 'i', 'o', 'u')
print('The hash for a tuple of vowels is:', hash(vowels))

# hash for a custom object
class Person:
    def __init__(self, age, name):
        self.age = age
        self.name = name
    def __eq__(self, other):
        return self.age == other.age and self.name == other.name
    def __hash__(self):
        return hash((self.age, self.name))
person = Person(23, 'Adam')
print('The hash for an object of person is:', hash(person))
```
```
carly@MSI MINGW32 ~/iot/lesson10 (master)
$ python hash_value.py
The hash for 1 is: 1
The hash for 1.0 is: 1
The hash for 3.14 is: 322818021289917443
The hash for Python is: -4245826223098274320
The hash for a tuple of vowels is: 6849294289590326869
The hash for an object of person is: -6402259473694034327

carly@MSI MINGW32 ~/iot/lesson10 (master)
$ python hash_value.py
The hash for 1 is: 1
The hash for 1.0 is: 1
The hash for 3.14 is: 322818021289917443
The hash for Python is: -3568684745831777106
The hash for a tuple of vowels is: -766554129811314493
The hash for an object of person is: 2031252093958142962
```
## Given commands:
```
$ cd ~/iot/lesson10
$ cat snakecoin.py
$ python3 snakecoin.py
```
## Results:
```
carly@MSI MINGW32 ~/iot/lesson10 (master)
$ cat snakecoin.py
# Gerald Nash, "Let's build the tiniest blockchain in less than 50 lines of Python"
import hashlib as hasher
import datetime as date

# Define what a Snakecoin block is
class Block:
  def __init__(self, index, timestamp, data, previous_hash):
    self.index = index
    self.timestamp = timestamp
    self.data = data
    self.previous_hash = previous_hash
    self.hash = self.hash_block()

  def hash_block(self):
    sha = hasher.sha256()
    sha.update(str(self.index).encode() + str(self.timestamp).encode() + str(self.data).encode() + str(self.previous_hash).encode())
    return sha.hexdigest()

# Generate genesis block
def create_genesis_block():
  # Manually construct a block with
  # index zero and arbitrary previous hash
  return Block(0, date.datetime.now(), "Genesis Block", "0")

# Generate all later blocks in the blockchain
def next_block(last_block):
  this_index = last_block.index + 1
  this_timestamp = date.datetime.now()
  this_data = "Hey! I'm block " + str(this_index)
  this_hash = last_block.hash
  return Block(this_index, this_timestamp, this_data, this_hash)

# Create the blockchain and add the genesis block
blockchain = [create_genesis_block()]
previous_block = blockchain[0]

# How many blocks should we add to the chain
# after the genesis block
num_of_blocks_to_add = 20

# Add blocks to the chain
for i in range(0, num_of_blocks_to_add):
  block_to_add = next_block(previous_block)
  blockchain.append(block_to_add)
  previous_block = block_to_add
  # Tell everyone about it!
  print("Block #{} has been added to the blockchain!".format(block_to_add.index))
  print("Hash: {}\n".format(block_to_add.hash))
```
```
carly@MSI MINGW32 ~/iot/lesson10 (master)
$ python snakecoin.py
Block #1 has been added to the blockchain!
Hash: e2877e40377d562f6d9d50f7b9cc953602fe3e30fad6a7abb72831d428f66927

Block #2 has been added to the blockchain!
Hash: fbbb7b7db87eb4bd1fb98a78ab63876e198a5e26d6836d171b5c4f02bed2812d

Block #3 has been added to the blockchain!
Hash: 464ed51143942aa4316ff9fa47003296aadc1f98022de950fb39d11823da4e5e

Block #4 has been added to the blockchain!
Hash: 6244b616b002f5c5cae25148c26cc3b0cfb82646235165eeb570cc3e8b7ede57

Block #5 has been added to the blockchain!
Hash: ff62177851b6634cf6667d6e705e30622fc5021f868386b763c9e7a35209cbcc

Block #6 has been added to the blockchain!
Hash: 87a13e7af2086628fa6c5e483bfaa44fd882d96b91b99bf5c1e1ed992b00c42a

Block #7 has been added to the blockchain!
Hash: 818bb8fcd92ecb073226ac6b60a88c43fb7973a5498578d5436140e50ba9ee91

Block #8 has been added to the blockchain!
Hash: 37dbf9f2534d4e3f711096d002fc34b1eb0c82327c75dbbe6d586b70985fc2f0

Block #9 has been added to the blockchain!
Hash: 3edfde80f5255972edf11ce64fd99ec3e947886baa68825cb977ecd3f4b6cead

Block #10 has been added to the blockchain!
Hash: 54d21adfa2ef38e2388849f33bf1778b4bae68609d8959054ff310f6ca053ea8

Block #11 has been added to the blockchain!
Hash: 2799fdd21591d2f743ffea2cca911ec4dc945b8bdef15b5673709d9b5780c657

Block #12 has been added to the blockchain!
Hash: 0e41f301ddecb7abe5d7e6be06141cf5ec9a10fa417c67a98b42296938a7b6be

Block #13 has been added to the blockchain!
Hash: 6b36216d4372a9eae02c93f288848d7871bb24e40675d3a9d0f773b2b13ce222

Block #14 has been added to the blockchain!
Hash: f6370a809419bf2150d733517db802d6bbc6d590448526389f4fed300a81df12

Block #15 has been added to the blockchain!
Hash: 05497709acd0dc12a4cf7919100e3171cb13ecda17cceaaad304c388c587ebbf

Block #16 has been added to the blockchain!
Hash: 0b2849815f0da0ae949c81dfc581e45f46c1f10d30528eb516769105419a0886

Block #17 has been added to the blockchain!
Hash: 40884c931c5d70d3830505451fcf79c43b917b4681f529282d4e6843e49b41cb

Block #18 has been added to the blockchain!
Hash: e54138eb8f1cfb82eb39e41803e72119d1186b4fbc83587b5b4eb141d6a87f60

Block #19 has been added to the blockchain!
Hash: 9ab7ef4f9cb51aec945d549ca64aa6eb78010a842e94b3c92ba61042bee98dd3

Block #20 has been added to the blockchain!
Hash: c29a6507ebb4d16d0b14df4f86d58af75e89f3cdba862a8aef56c09a98ea6691

```
 ## Given commands:
```
$ cat snakecoin-server-full-code.py
$ python3 snakecoin-server-full-code.py
$ cd
```
## Results:
```
carly@MSI MINGW32 ~/iot/lesson10 (master)
$ cat snakecoin-server-full-code.py
# Gerald Nash, "Let’s Make the Tiniest Blockchain Bigger Part 2: With More Lines of Python"
# Referred to https://www.pythonanywhere.com/forums/topic/12382/ that fixed sha.update() TypeError: Unicode-objects must be encoded before hashing
# Running on http://127.0.0.1:5000/mine (Reload the page to mine and press CTRL+C to quit)
from flask import Flask
from flask import request
import json
import requests
import hashlib as hasher
import datetime as date
from flask import send_from_directory
import os
node = Flask(__name__)

# Define what a Snakecoin block is
class Block:
  def __init__(self, index, timestamp, data, previous_hash):
    self.index = index
    self.timestamp = timestamp
    self.data = data
    self.previous_hash = previous_hash
    self.hash = self.hash_block()

  def hash_block(self):
    sha = hasher.sha256()
#    sha.update(str(self.index) + str(self.timestamp) + str(self.data) + str(self.previous_hash))
    sha.update((str(self.index) + str(self.timestamp) + str(self.data) + str(self.previous_hash)).encode("utf-8"))
    return sha.hexdigest()

# Generate genesis block
def create_genesis_block():
  # Manually construct a block with
  # index zero and arbitrary previous hash
  return Block(0, date.datetime.now(), {
    "proof-of-work": 9,
    "transactions": None
  }, "0")

# A completely random address of the owner of this node
miner_address = "q3nf394hjg-random-miner-address-34nf3i4nflkn3oi"
# This node's blockchain copy
blockchain = []
blockchain.append(create_genesis_block())
# Store the transactions that
# this node has in a list
this_nodes_transactions = []
# Store the url data of every
# other node in the network
# so that we can communicate
# with them
peer_nodes = []
# A variable to deciding if we're mining or not
mining = True

@node.route("/")
def hello():
    return "SnakeCoin Server"

@node.route('/favicon.ico')
def favicon():
    return send_from_directory(os.path.join(node.root_path, 'static'),
                               'favicon.ico',
                               mimetype='image/vnd.microsoft.icon')

@node.route('/txion', methods=['POST'])
def transaction():
  # On each new POST request,
  # we extract the transaction data
  new_txion = request.get_json()
  # Then we add the transaction to our list
  this_nodes_transactions.append(new_txion)
  # Because the transaction was successfully
  # submitted, we log it to our console
  print("New transaction")
  print(("FROM: {}".format(new_txion['from'].encode('ascii','replace'))))
  print(("TO: {}".format(new_txion['to'].encode('ascii','replace'))))
  print(("AMOUNT: {}\n".format(new_txion['amount'])))
  # Then we let the client know it worked out
  return "Transaction submission successful\n"

@node.route('/blocks', methods=['GET'])
def get_blocks():
  chain_to_send = blockchain
  # Convert our blocks into dictionaries
  # so we can send them as json objects later
  for i in range(len(chain_to_send)):
    block = chain_to_send[i]
    block_index = str(block.index)
    block_timestamp = str(block.timestamp)
    block_data = str(block.data)
    block_hash = block.hash
    chain_to_send[i] = {
      "index": block_index,
      "timestamp": block_timestamp,
      "data": block_data,
      "hash": block_hash
    }
  chain_to_send = json.dumps(chain_to_send)
  return chain_to_send

def find_new_chains():
  # Get the blockchains of every
  # other node
  other_chains = []
  for node_url in peer_nodes:
    # Get their chains using a GET request
    block = requests.get(node_url + "/blocks").content
    # Convert the JSON object to a Python dictionary
    block = json.loads(block)
    # Add it to our list
    other_chains.append(block)
  return other_chains

def consensus():
  # Get the blocks from other nodes
  other_chains = find_new_chains()
  # If our chain isn't longest,
  # then we store the longest chain
  longest_chain = blockchain
  for chain in other_chains:
    if len(longest_chain) < len(chain):
      longest_chain = chain
  # If the longest chain isn't ours,
  # then we stop mining and set
  # our chain to the longest one
  blockchain = longest_chain

def proof_of_work(last_proof):
  # Create a variable that we will use to find
  # our next proof of work
  incrementor = last_proof + 1
  # Keep incrementing the incrementor until
  # it's equal to a number divisible by 9
  # and the proof of work of the previous
  # block in the chain
  while not (incrementor % 9 == 0 and incrementor % last_proof == 0):
    incrementor += 1
  # Once that number is found,
  # we can return it as a proof
  # of our work
  return incrementor

@node.route('/mine', methods = ['GET'])
def mine():
  # Get the last proof of work
  last_block = blockchain[len(blockchain) - 1]
  last_proof = last_block.data['proof-of-work']
  # Find the proof of work for
  # the current block being mined
  # Note: The program will hang here until a new
  #       proof of work is found
  proof = proof_of_work(last_proof)
  # Once we find a valid proof of work,
  # we know we can mine a block so
  # we reward the miner by adding a transaction
  this_nodes_transactions.append(
    { "from": "network", "to": miner_address, "amount": 1 }
  )
  # Now we can gather the data needed
  # to create the new block
  new_block_data = {
    "proof-of-work": proof,
    "transactions": list(this_nodes_transactions)
  }
  new_block_index = last_block.index + 1
  new_block_timestamp = this_timestamp = date.datetime.now()
  last_block_hash = last_block.hash
  # Empty transaction list
  this_nodes_transactions[:] = []
  # Now create the
  # new block!
  mined_block = Block(
    new_block_index,
    new_block_timestamp,
    new_block_data,
    last_block_hash
  )
  blockchain.append(mined_block)
  # Let the client know we mined a block
  return json.dumps({
      "index": new_block_index,
      "timestamp": str(new_block_timestamp),
      "data": new_block_data,
      "hash": last_block_hash
  }) + "\n"

node.run()
```
```
carly@MSI MINGW32 ~/iot/lesson10 (master)
$ python snakecoin-server-full-code.py
 * Serving Flask app 'snakecoin-server-full-code'
 * Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on http://127.0.0.1:5000
Press CTRL+C to quit
127.0.0.1 - - [04/May/2023 18:11:48] "GET / HTTP/1.1" 200 -
127.0.0.1 - - [04/May/2023 18:11:49] "GET /favicon.ico HTTP/1.1" 200 -
```
![image](https://user-images.githubusercontent.com/117042826/236340774-92d8c1d9-b0e5-4619-8d61-c566b13a5c6b.png)

## Given commands:
```
$ curl "localhost:5000/txion" \
     -H "Content-Type: application/json" \
     -d '{"from": "akjflw", "to":"fjlakdj", "amount": 3}'
$ curl localhost:5000/mine
```
## Results:

![image](https://user-images.githubusercontent.com/117042826/236341629-4aee24b7-1d4d-403c-9d2d-74ab00f252ab.png)











