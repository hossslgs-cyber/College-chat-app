WEB-APP COSTING $0
FRONTEND: React + Vite on Vercel.
 BACKEND: Node.js + Express + Socket.io on Render. 
DATABASE: MongoDB Atlas M0. AUTHENTICATION: Clerk.

Node.js uses a non-blocking event loop to handle 50 concurrent WebSocket connections efficiently on one free Render instance. MongoDB’s flexible schema eliminates migration downtime when adding reactions or file uploads. React + Vite enables instant UI interaction, while Clerk provides secure auth and profiles in 10 lines critical for students who abandon apps with poor login UX.

TRADEOFF: Chose MongoDB over PostgreSQL. Gain fast iteration and schema flexibility lose native JOINs and complex relational modeling. MongoDB supports ACID transactions, but chat is append-heavy with minimal cross-document writes, so transaction overhead isn’t needed. Indexed by chatRoomId + timestamp and rate-limited (5 messages/sec) to prevent spam.
Scales to 1000 users before requiring paid infrastructure.