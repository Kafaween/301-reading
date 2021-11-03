# HashTable

## What is a HashTable

Terminmolog|---|---|
---|---|---
Hash - A hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose. In the case of a hashtable, it is used to determine the index of the array.|Buckets - A bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.|Collisions - A collision is what happens when more than one key gets hashed to the same location of the hashtable.

## What is the benifits of Hash ,Buckets,Collisions

1. Hold unique values
2. Dictionary
3. Library

**Hashtables** are a data structure that utilize key value pairs. This means every Node or Bucket has both a key, and a value.

**Note** The basic idea of a hashtable is the ability to store the key into this data structure, and quickly retrieve the value.


## Structure

**Hashing** hash code turns a key into an integer. It’s very important that hash codes are **"deterministic"**: their output is determined only by their input. Hash codes should never have randomness to them. The same key should always produce the same hash code.
