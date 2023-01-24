The application I chose to write that does this is a banking application. I chose that because it naturally matches a lot of these use cases, especially around the writing to Queues and batch processing nature required to run quarterly / yearly financial reports. It was entirely too much work and most of my work actually went into understanding double entry bookkeeping and how to build a data model that would allow US regulation compliance for financial reporting. I went pretty far in the weeds on the financial accuracy aspect. This also took forever. It's a job for multiple people TBH. That's why it was an aspiration project.

Fullstack applications that supports:

- Server side rendering (SSR)
	- want to see a proper layout with fragments implemented
	 - you could use a subdomain to point at this particular version vs the frontend JS version
	  - Keep this version in parity with your Frontend application supported by your API
- API
	- make it versioned
	 - have authorization - make at least 3 different roles. hide pages or functionality behind different roles
	  - have authentication
	   - use swagger, but turn it off in higher environments
- Deploy this to the cloud in a docker container
- Front-End Client (JS/TS)
	- React
	- I want to see you manage roles and permissions properly here as well.
		- bit of a trick here as most frontend frameworks actually end up going SSR here because there is no real good way to keep content locked behind authentication/auth if it's all shipped with the frontend code. Sometimes people even make separate frontend applications for different users.
	- Want to see you manage state properly
	- want to see the ability to deep-launch from links
	- How do you handle errors / network outages / service issues
	- keep this and your SSR version in parity, feature wise and style wise
- Make these apps support OpenID, Oath2 and standard cred login.
	- I want to see your security filter chain and how your app handles multiple login providers
	- make that work with session management
- Make use of service layer caching with Redis or something similar
- Make use of a Queue
	- bonus points if you write a console app that interacts with that queue on a scheduler
- Display use of an ORM
- Display proper levels of abstraction that also fit with your chosen web framework's typical project structure. Please don't have some goofy off the wall project structure
- Add your DB scripts.
	- bonus points if you come up with a reason for a complicated SQL Stored procedure with a CTE
	- Make sure you have a good and optimized DB structure.
		- optimized for what??? you decide!
- Have more than one data source
	- use that other data source as a fallback or for storing other type of information (maybe some observability metrics or error logs)
- WRITE unit and integration test suite. See if you can get a high coverage 70-80 percent. If your application isn't testable, you're probably not following your SOLID principles well.
- Mega ultra bonus points !!!!!!!!!! Write a design specification for this application.

This is a bit of a silly project because you're kind of working backwards to make the project fit the engineering for most examples, but you're trying to make a showcase here... you're trying to stand out. Coming up with a project that could necessitate all this shit is impressive in it's own right.

https://www.reddit.com/r/PHP/comments/104id6p/looking_for_ideas_that_a_senior_web_developer_can/

gRPC vs REST vs GraphQL
https://www.reddit.com/r/programming/comments/nqhngc/grpc_vs_rest_comparing_apis_architectural_styles/
https://blog.logrocket.com/node-js-orms-why-shouldnt-use/

gRPC (streaming?)
Protocol buffers (Protobufs)

GoLang
	frameworks
		Gin
		Echo
		 net/http (stdlib)
	routers
		stdlib/servermux
		chi
		gorilla/mux
	gRPC
	http-proxy

Object-relational mapping (ORM)
	Prisma
	Sequelize
	Knex
	Node Postgres Driver
	Mongoose? (NoSQL)
	entgo
	sqlx


https://docs.google.com/document/d/1pgMutdDasJb6eN6yK6M95JM8gQ16IKacxxhPXgeL9WY/edit