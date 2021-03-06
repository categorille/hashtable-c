# C Hashtable Implementation

This is a simple implementation of a string-to-string hashtable (both keys and
values are strings). The hash function used is
[FNV-1a](http://www.isthe.com/chongo/tech/comp/fnv/index.html#FNV-1a).
Collision resolution is done using linear probing.

## Compilation

The prompt can use readline for autocompletion of commands and better line
editing capacities. Otherwise, a homebrewed prompt implementation will be used,
which should work but isn't as nice to use.

- with readline: `gcc hashtable.c prompt.c main.c -D _USE_READLINE -lreadline`
- without readline: `gcc hashtable.c prompt.c main.c`

## Usage

The user is presented with a simple prompt. A few commands can be issued.
Arguments are space or tab-separated, with no support for including whitespace
characters in arguments yet.

- `exit`, `quit` or `q`: exit the program.
- `put`: add the given key-value pair to the hashtable. Requires two arguments
  (key and value).
- `remove`: attempt to remove the entry with the given key from the hashtable.
  Requires one argument (key).
- `show`: display information about the hashtable, such as capacity, load
  factor, and existing key-value pairs. Requires zero arguments.
- `hash`: display the hash value of the first argument in base 16. If there is
  a second argument, and it is a valid positive non-zero integer, show hash of
  first argument modulo second argument, in base 10.
