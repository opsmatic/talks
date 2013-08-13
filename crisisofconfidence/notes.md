# Monitoring - it's not just for numbers

"Much time and mindshare is dedicated to monitoring. Primarily monitoring is
associated with looking at numbers over time and, if alerting is included under
the monitoring umbrella, being alerted when those numbers don't behave the way
we expect them to. However, only looking at numbers and service states leaves us
with just the tip of the iceberg. We will look at how our alerts and numbers can
be enhanced greatly by adding some context from non-numeric, and non-binary
observations. We will fantasize about what our tools might look like if we tried
to surround ourselves with helpful contextual information, as well as look at
some concrete examples."

### TODOs
* reach out to Marcus B about using screenshots as examples

We talk about monitoring a lot. In fact, we have entire conferences about them.
What do we mean by monitoring?

Thresholds

Many of the well known, widely used monitoring tools to some extent look at
thresholds.

# Control

The sensation of control can come from many sources. It can come from not
letting other people do anything. It can also come from having a firm knowledge
of the state of things and on being meaningfully apprised of events that change
this state.

The latter can also be achieved in different ways. It can be achieved by forcing
a certain process for changes that involves re-baking the infrastructure every
time something changes. But it can also come from good tools that give you
insight and context.

You can feel in control because there's a way of quickly finding out how things
are and how they got there.

# Types of data

Traditional monitoring primarily deals with numeric data - means, percentiles,
rates, etc. One exception we're seeing more and more is monitoring for binary
states (service running or not). What about strictly non-numeric data? Who is
logged on? What packages are installed?

Traditionally that sort of information is collected as part of a specific goal
(security, audits, etc) or as part of configuration management. But what if
instead of only caring about packages and configuration file contents during a
CM run, you collected this information on an ongoing basis and kept track of
when it changed?

__Resource:__ Quote from John Vincent "Availability isn't binary"
https://groups.google.com/d/msg/devops-toolchain/yMSS1FjwTwo/aXM5AXKvSsYJ

# Context

Context is invaluable to an operator when performing their job. I'm not new in
saying this, we've heard it from all sorts of places. When you receive an alert,
you want to know "what's going on." In traditional monitoring.

# Log monitoring

High volume, often looked at in aggregate (aka, turned into numbers). Splunk,
Sentry.

# Narrowing

Actual surface area of differences between hosts is likely minimal, yet it's
impossible to know where to look. Is it a package? Is it a particular config
value? Is it a `sysctl` value? Is it a bios setting that only shows up in
`cpuinfo`?


