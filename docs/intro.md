---
sidebar_position: 1
slug: /
---

# Introduction

## What Is Segment?
Segment is a *simple* and *fast* in-memory database written in [Rust](https://www.rust-lang.org/). It has a key-value data model which means that you can store key-value data in it. It is meant to store ephemeral data (caches etc.) and should not be used as a primary database.

## Why Segment?
Segment has the concept of *keyspaces*, which means that related keys can be stored together, think of keyspaces as tables in a traditional relational database. Keyspaces are dynamic which means that you can create as many as you like. Segment goes one step further by allowing you to configure keyspaces individually, for example let's say you have 2 keyspaces `a` and `b` you can set separate eviction policies for them, this providies a lot of flexibility to the developer, you can have one keyspace have an LRU policy while the others can have no eviction at all.

## Interested?
If this seems intersting, you can checkout the [getting started ](getting-started/installation) guide to install segment and play with it. Be mindful that Segment is in it's very early stages and can have issues and is not yet production ready at all.
