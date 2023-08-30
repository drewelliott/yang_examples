# YANG examples

**The goal is learning to understand how to create YANG models.**

The example here is a YANG model for a network engineer - this is easy to understand as most people reading this already understand what a network engineer is, so it removes anything that might cause confusion.

Additionally, we are importing the ietf-inet-types YANG model and using it in our network-engineer model.

There is also an example of using pyang to see the tree of the YANG model we created

[pyang](https://pypi.org/project/pyang/) is a very useful tool for exploring YANG models.

One of its features is the ability to output a tree representation of a YANG model.

`pyang -f tree <yang model file>`

```
╭─drew@snoopy ~/git/yang_examples ‹pyang_tree●› ‹venv› 
╰─$ pyang -f tree network-engineer.yang 
module: network-engineer
  +--rw network-engineer
     +--rw name?                 string
     +--rw email?                string
     +--rw experience?           engineer-level
     +--rw configured-devices* [device-name]
        +--rw device-name             string
        +--rw device-type?            string
        +--rw device-ip?              inet:ipv4-address
        +--rw configuration-status?   boolean 
```