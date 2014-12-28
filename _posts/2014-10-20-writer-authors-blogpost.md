---
layout: post
date: 2014-10-20 15:12
title: "writer >AUTHORS blogPost."
author: sj
---

[This Is A Work In Progress, A Funny Way Of Saying This Is Unfinished.]

# Getting The Knowledge Into The Machine.

There are more than a few textual formats for graph input and queries. _Notation3_ (`n3`) is an informal syntax for RDF data, which in itself is a specific format for semantic web data. The semantic web in short is the idea of linking all information and knowledge in a massive distributed data warehouse for reuse.  It is an exciting and futuristic idea... but fraught with dangers if you don't know who controls|controlled the data. So this is not as interesting to me as what I might do if I could rapidly capture information as easily as I could manipulate text with Vim. Vim is extremely terse, which can put off many new users. I don't think that graph input has to be that extreme. 

Semantic data still brings a lot of W3C baggage along for the ride with XML namespaces and an assumption of assertions of "subject verb object."  N3 assertions look like `<#pat> <#knows> <#jo> .` or `:Pat a :Person.` From a keyboard standpoint, stream of consciousness typing of N3 will involve a lot of abuse upon the Shift-keys for the symbols. 

N3 is certainly easier to write than RDF, but not quite at the level of "Wiki Link" easy, where some knowledge of textual conventions can remove most syntax. For anyone who has never heard of a WikiLink, you'll notice that it exploits a "hole" of the English language where NamesWithCapitalLettersMashedTogether are not commonly used.  These words can be easily scanned and extracted with a regular expression parser to make them special, typically replacing them with a link to another document.

The _Graph Entity Offline File Format_ (`GEOFF`) is another format that brings us closer to a generalized graph data language used in the Neo4j world. More complicated graph constructions of points and edges look like: 

`(a {"name":"Alice"})<-[:KNOWS]->(b {"name":"Bob"})<-[:KNOWS]->(c {"name":"Carol"})<-[:KNOWS]->(a)`

That's a lot of code. While I have edge directions `>` and `<`, I haven't introduced the double-edge, going in both directions. I use `=` for that. So the above would be written:

`a {name: "Alice"} =KNOWS b {name: "Bob"} =KNOWS c {name: "Carol"}`

This also adds attributes to the data, but not _types_ or what Neo4j calls labels. I would add the curly brace container for attributes, but lose the mandatory quoting of attribute names, giving us:

`writer {name: "Simon"} >AUTHORS blogPost.`

Adding in a type for the writer point (this example leaves out the >EDGE and direct object symbol) would look like:

`writer:Person {name: "Simon"}` 

Having a type gives an interactive tool a hint to which attributes to arrange for a template form. 

Since this is graph data, there isn't an "English" convention to work inside. We set rules for different kinds of data via textual format:

1. `identifierText` text not beginning with a capital are symbols for points.
2. `UPPERCASE` text are symbols for edges.
3. `TitleCased` text are symbols for types.

# Defining The Primitives

Meanwhile, we've introduced a lot of terminology, let's collect the terms together here:

**identifier** A name for a value.

**value** An instance of data.

**type** An identifier of a kind of value.

**point** A value connected with edges.

**edge** A connection between points.

**attribute** A {identifier: value} associated with other values including types, points, edges and other attributes.

# Querying What You've Encoded.

N3 isn't a query language, however, for the W3C's part, they are working on SPARQL, which looks a bit like SQL. This irks me a bit because it isn't isomorphic with N3|RDF.  I used `writer >AUTHORS blogPost` earlier to assert the existence of a writer (unamed) that has authored a `blogPost` (untitled).  How to then get the data back out?  Let's ask for authors: `* >AUTHORS`. If we flip the direction of the edge, `* <AUTHORS` we should get blog posts. If we want both in a pair of sets, `* >AUTHORS *` would return those.  Say that we have two kinds of points that create blog posts, `Person` and `Organization`. To get only organizations that author, we add a type to the query: `*:Organization >AUTHORS`. To get people, `*:Person >AUTHORS`. To get only blog posts written by organizations: `* <AUTHORS ~:Organization`. Here I'm using a tilde (`~`) to indicate that I'm requesting points of a certain type, but I do not want the set of points returned with the result.
