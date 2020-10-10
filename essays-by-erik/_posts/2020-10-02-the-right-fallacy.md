---
layout: post
title: The "Right" Choice
---
In ~~business~~ decision-making, there's rarely a clear, right choice.

There are usually some objectively wrong or bad choices.

There are often several good or fine choices.

This is good news!

Is a relational database better than a no-SQL database? It depends.

_This particular example hit the whole point of this essay home for me several years ago at Duo. [We were moving](https://duo.com/blog/building-better-reports-with-a-data-pipeline){:target="_blank"} away from MySQL to store records of authentications. After growing a table to several billion records and continuing to add hundreds of millions more per month, making changes to the schema was onerous and caused outages. Further, it was nearly impossible for us to flexibly search, filter, and aggregate the data (a problematic outcome when we had customers screaming for robust reports to demonstrate how Duo was performing for them). We chose to move to Elasticsearch. What it made up for in the benefits of flexible schema, searching, and aggregation, we felt the tradeoff of cluster maintenance and a lack of relational data capabilities._

Most decisions are not about picking the right choice but rather being aware of the appropriate tradeoffs.

Org design decisions are no different. There is no best org design.

Are teams of full-stack developers focused on a single product better than teams of specialists? It depends.

What tradeoffs do you want to make? Neither is problem free so you're really making a design decision about how you want to operate going forward. As Churchill said, "...we shape our buildings and afterwards our buildings shape us."

Academically, it's easy to see that there being a single, right choice is often not the right issue to focus on. Economists figured this out long ago. Vilfredo Pareto developed the idea of [Pareto Optimality or Pareto Efficiency](https://en.wikipedia.org/wiki/Pareto_efficiency){:target="_blank"}.

<img src="https://www.economicshelp.org/wp-content/uploads/2017/07/pareto-efficiency-2017.png.webp" alt="Curve demonstrating a set of pareto optimal choices." width="450px"/>

In the economists' model, it's straightforward to chart the pareto curve and the options that are all optimum. It's easily quantifiable.

Practical application is more difficult though.

Developers desire clearcut answers. However, software engineering is more art than science. The name belies how subjective the field is. Can you really quantify the benefits of Rust over Python? I doubt it (although someone invariably has or will try).

Luckily though, most decisions don't need an optimal choice. They just need a good enough one. [Pareto](https://en.wikipedia.org/wiki/Pareto_principle){:target="_blank"} figured this out too. 80% of the effects come from 20% of the causes.

Stop asking if something is the right choice. Instead, ask if it's a reasonable, good enough choice. Make the decision. Then move on.
