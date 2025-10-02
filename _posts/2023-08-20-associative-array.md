---
layout: post
title: Associative Array
date: '2023-08-20 13:29:28 +0530'
categories:
  - Blog
tags: []
comments: []
---

<div style="text-align: center;">
   <img src="/assets/images/2023-08-20-associative-array.jpg" alt="Associative Array image" style="max-width: 300px; width: 100%; height: auto; display: block; margin: 0 auto;" />
   <div style="font-size: 0.9em; color: #555; margin-top: 8px;">
      <em>Image by <a href="https://www.pexels.com/photo/various-footwear-for-selling-placed-on-stone-on-street-6129795/">Quang Nguyen Vinh via pexels.com</a></em>
   </div>
</div>

Recently I came across the term **Associative Array**. For whatever reason, I had never heard of this term before, also, I can't remember hearing this from my bachelor's course as well. I asked a few of my friends, some of them had not heard about it as well...

I wanted to learn about what and how this term is defined and its usage wrt programming languages. These notes are a compilation of my readings online…

After a quick Google search, we would see that **Hash Table** is one of the concrete implementations of Associative Array ADT. However, there are several interesting references about it online.

---

The [Wikipedia article](https://en.wikipedia.org/wiki/Associative_array) is quite amazing and a few important points are:

- Major implementations are [hash tables](https://en.wikipedia.org/wiki/Hash_table) and [search trees](https://en.wikipedia.org/wiki/Search_tree).
- There is also hardware-level support for associative arrays called [Content-addressable Memory](https://en.wikipedia.org/wiki/Content-addressable_memory).

## Definition

> An **associative array**, **map**, **symbol table**, or **dictionary** is an [abstract data type](https://en.wikipedia.org/wiki/Abstract_data_type) that stores a [collection](https://en.wikipedia.org/wiki/Collection_(abstract_data_type)) of [key, value pairs](https://en.wikipedia.org/wiki/Attribute%E2%80%93value_pair), such that each possible key appears at most once in the collection.  
> — [wiki](https://en.wikipedia.org/wiki/Associative_array#:~:text=In%20computer%20science%2C%20an%20associative,most%20once%20in%20the%20collection.)

## Operations

> - **Insert** or **put**: add a new `(key, value)` pair to the collection, mapping the key to its new value. Any existing mapping is overwritten. *The arguments to this operation are the key and the value.*
> - **Remove** or **delete**: remove a `(key, value)` pair from the collection, unmapping a given key from its value. *The argument to this operation is the key.*
> - **Lookup**, **find**, or **get**: find the value (if any) that is bound to a given key. *The argument to this operation is the key, and the value is returned.*  
> — [wiki](https://en.wikipedia.org/wiki/Associative_array#Operations)

More generalization seems to support:

- iteration: loop over mappings (order left to the implementation)
- multimap: multiple values associated with a single key
- bidirectional map: lookup possible with both key and reverse lookup with value

---

## Other References

As I checked online forums such as Stack Overflow, Quora, and GeeksforGeeks, I found confusion around whether an associative array is indexed both on integer and key, and whether it is iterable in insertion order.  
Both are not required by the ADT definition — those properties belong to specialized containers like Ordered-Map or Ordered-Dictionary.

**This C++ thread seemed spot on**:

> Arrays are generally indexed by position. A simple array `int x[10]` has elements `x[0] ... x[9]`. The index is an unsigned integral value.  
> The associative container means that the index can be arbitrary (e.g., `std::string`).  
> — [What is the meaning of associative array?](https://stackoverflow.com/questions/15249743/what-is-the-meaning-of-associative-array)

Other examples:

- [Java associative-array](https://stackoverflow.com/questions/5122913/java-associative-array)  
- [Access data in python3 associative arrays](https://stackoverflow.com/questions/73392878/access-data-in-python3-associative-arrays)  
- [How to convert an associative array in python?](https://stackoverflow.com/questions/7286111/how-to-convert-an-associative-array-in-python)  
- [Python: Create associative array in a loop](https://stackoverflow.com/questions/3994345/python-create-associative-array-in-a-loop)

GeeksforGeeks: [Implementing Associate Array in Java](https://www.geeksforgeeks.org/implementing-associate-array-in-java/)  
Quora: [Are associative array and hash table basically the same things?](https://www.quora.com/Are-associative-array-and-hash-table-basically-the-same-things)

---

## PHP Arrays

Particularly interesting was this PHP example: `$arr[0]['name'] = 'demo';`. There are **two put operations**: one implicit (for nested keys) and one explicit (assignment). This differs from Java or Python.

From the [PHP manual](https://www.php.net/manual/en/language.types.array.php):

> An array in PHP is actually an ordered map. A map is a type that associates values to keys… optimized for several uses (array, list, hash table, dictionary, stack, queue, etc.).

**Example:**

```php
$arr = array();

$arr[0]['name'] = 'demo';
$arr[0]['fname'] = 'fdemo';
$arr[1]['name'] = 'test';
$arr[1]['fname'] = 'fname';

var_dump($arr);
```

PHP also supports deep implicit puts:

```php
$arr2 = array();
$arr2['k0']['k00']['k000']['k0000'] = 'v0';
var_dump($arr2);
```

---

## Key Takeaways

1. Associative Array is an **ADT**, while a hash table is a concrete implementation.  
   Implementations in languages: **Map** (Java, C++), **Dictionary** (Python).  
   Ordered maps often use trees (e.g., C++ `std::map`).
2. PHP Arrays are unusual — they unify array, list, stack, queue, map, etc.  
   Likely with performance trade-offs.
3. PHP associative array usage (nested key assignment) shows implicit operations that feel like "magic."
