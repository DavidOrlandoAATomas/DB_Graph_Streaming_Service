Neo4j NoSQL Database Model for a Streaming Service

This project demonstrates a graph-based NoSQL database model using Neo4j to represent a streaming service ecosystem.
Instead of rigid tables, the system models users, movies, series, actors, directors, and genres as nodes, with meaningful relationships connecting them.

The goal is to show how graph databases naturally represent entertainment data, where relationships are first-class citizens.

📌 Technologies Used

Neo4j

Cypher Query Language (CQL)

NoSQL (Graph Database Model)

🧠 Domain Model Overview

The model represents a typical streaming platform where:

Users watch movies and series

Movies and series belong to genres

Actors act in movies and series

Directors direct movies and series

Users can rate what they watch

Graph databases are ideal here because queries like
“Which movies did users who liked X also watch?”
or
“Which actors frequently appear in Action movies?”
become intuitive and efficient.

🧩 Node Types
Label	Description
USER	Represents platform users
MOVIE	Represents movies
SERIES	Represents TV series
ACTOR	Represents actors
DIRECTOR	Represents directors
GENRE	Represents movie/series genres

🔗 Relationship Types
Relationship	From → To	Description
WATCHED	USER → MOVIE / SERIES	User watched content (may include rating)
ACTED_IN	ACTOR → MOVIE / SERIES	Actor participated in content
DIRECTED	DIRECTOR → MOVIE / SERIES	Director directed content
IN_GENRE	MOVIE / SERIES → GENRE	Content belongs to a genre

⭐ Relationship Properties

WATCHED.rating: User’s rating for the movie or series

Some relationships include extra properties such as title, demonstrating Neo4j’s flexibility

🗂 Example Graph Structure
(USER)-[:WATCHED {rating}]->(MOVIE)
(ACTOR)-[:ACTED_IN]->(MOVIE)
(DIRECTOR)-[:DIRECTED]->(MOVIE)
(MOVIE)-[:IN_GENRE]->(GENRE)
