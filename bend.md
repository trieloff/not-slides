# Bending your Brain for Serverless Success

Lars Trieloff

---


1. First step to successfully bending your brain is admitting that your brain needs bending: serverfull habits die hard.

---

2. Why would you want to bend your brain in the first place: because serverless is the most disruptive change to enterprise software of the last two decades (What about mobile? We had fat clients before! What about the Cloud? We had mainframes before! What about AI? We had complicated IF statements before)

---

3. Serverless is disruptive because it challenges the architecture of your software. Just like rebar changed what could be done, it changes what can be done – but it also changes what must be done.

---

4. What is architecture about? Many would say: architecture is about the mastery of best practices. But that's wrong: architecture is about trade-offs and constraints. Best practices are canned trade-offs made for pre-existing constraints. When the constraints change, you must re-evaluate your trade-offs.

---

5. Two examples:
6. Exhibit A: In a traditional computing world, buying hardware costs money. In a traditional cloud world, having instances running costs money. That's why we came up with a good trade-off between cost and ability to test without interrupting production: the trinity of dev-stage-prod. In a serverless world, having a function is free (as long as you don't run it), so there is no need to limit yourself to having only three versions of each function: you can have an infinite amount.

---

7. Exhibit B: In traditional computing, one of the hardest problems is concurrency. In serverless, concurrency is still a hard problem, but one aspect of it, parallelism has become very easy (and when I say very easy, I mean: someone else's problem). Before serverless, you had a limited number of jobs you could run in parallel before you ran out of resources. In the serverless world, these limits are just a setting in your AWS account preferences. Running a small job for every customer at once? Just do it, the runtime will figure out how and when to do it.

---

8. Servers are an implementation detail. In every serverless presentation there is always one guy (and it's always a guy) who needs to point out: but there are still servers!. The point of serverless is not that there are no servers – the point is that the servers could go away and we wouldn't mind.  If you figure out a way to offer serverless computing without using containers, or without using virtual machines, or without using real machines and instead use the brain waves of the magic quantum computing fairy, no serverless developer would bat an eye, as long as you don't break the API contract. In fact, if you promise lower cost or lower latency, they will be thrilled by it.

---

9. Serverless is the application of functional programming concepts to software architecture. And just like functional programmers abhor side-effects and try to shield them with three layers of magic and monads (that's like Dungeons and Dragons, but with a LISP), serverless architects abhor state and try as much as possible to make it someone else's problem, either through event-based architectures, caches or cloud-based storage services. We love the convenience of this infrastructure, but just like indoor plumbing, while you might value the convenience, getting too enthusiastic about the plumbing will just make you look weird.

---

10. I said architecture is about constraints and in fact constrains are what shape architecture. You know a constrain when no amount of meetings can make it go away. The hardest constraint in serverless is Latency. The solutions to serverless latency are: making it irrelevant through event-based processing (that's why people talk less about event-based architectures being a core pattern of serverless as serverless Plattform are successful in reducing latency). Another solution is caching (i.e. now you've got a cache invalidation problem) and reducing function size.

---

11. The wrong way to solving latency is to focus on cold start latency only and thinking that you can avoid cold starts by somehow keeping your functions "warm" by constantly pinging them. Not only have you pushed your latency problem away to the point in time when your application is under variable load and needs to auto-scale, thus making it harder to trace, you've also brought back servers through the back door.

---

12. Remember what I told you about admitting that you have a problem: keeping functions warm is a sign of acute server addiction. Other signs are: 
	- long running functions
	- "Persistent" functions
	- Mega-Functions that do more than one thing and have "routes"

---

11. Yes, you will end up with many, many, many functions. But remember: there is no problem in serverless that can't be solved by adding another function. Except the problem of having too many functions. But you can try.

---

12. You all know about cattle vs. pets. In the serverless world, if you think about your functions as cattle, i.e. if you think about it like a rancher on a server farm, you've already lost. Think like a beekeeper instead. You want to keep your functions small, disposable and uniform, so that you can handle them in bulk. Uniformity means: deploy them all in the same way, get log data in the same way, do monitoring in the same way, etc. btw. Functional programming concepts like wrapping functions in functions can help a great deal here

---

13. Monitoring: essential because legibility of Serverless architectures is limited. Many services and everything is ephemeral. By the time you’ve figured out there is a problem, it most likely already went away. But problems that disappear spontaneously, also reappear spontaneously.

---

13. To sum it up: Serverless computing is the future, but you won't get it for free. Like all people who are living with one step in the future, members of the serverless tribe can seem a bit odd, but that's only because they in the process of getting their brains bent. On the other hand, they are a really friendly and helpful group of people, so if you are wondering if serverless could be right for you, reach out and ask us.
