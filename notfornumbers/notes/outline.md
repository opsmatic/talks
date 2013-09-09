# A Crisis of Confidence

There's a crisis of confidence in progress.

People don't trust machines anymore.

> "One of the scariest things I ever encounter is a server that’s been running
> for ages which has seen multiple upgrades of system and application software."
> - Chad Fowler

Machines drift. No matter how much you automate and chef and puppet, they still
drift.

Years of whack-a-mole has made developers turn back to dark times.

![norton ghost]()

This mistrust is misplaced. Machines don't drift. People make machines drift.

People don't trust -machines- people anymore.

![something sad, possibly people facing away from each other with mistrust]()

Why? Because people gotta get shit done.

It's the same old song and dance - individuals often find themselves at odds
with other individuals in the same organization, though the end goal is
seemingly the same.

John Allspaw talked about the job of Operations - "Enable the Business." This is
just polite for "Get shit done" - same as everyone else's job.

GST is the new DevOps

(Unfortunately, "Get shit done" has been indirectly ruined by this guy)

![get things done](thingsdone.jpg)

Unfortunately, the tools and processes that are emerging are somewhat
antithetical to dev/ops cooperation as John and Paul envisioned it, or at least
the way I interpreted it and the way it happened at Flickr when I got there.

Instead of dev/ops cooperation, we have an increasing concentration of domain
knowledge and process in ops organizations, which are just being renamed to
DevOps organizations to indicate a penchant for automation and CI.

In the meantime, that shit's still gotta get done.

** Outages ** There's no time to run __insert your CD tool here__  when the site
is on fire. DEFINITELY no time to cook a new AMI and provision a bunch of new
machines. The problem of "OK, we fixed it, but what the fuck have we done to get
here over the past 4 hours" is largely unsolved.

_TODO_ Derek outage stories - extra queue, etc

** Debugging ** The best place to debug a prod problem is in prod. Deal with it.

** Experimentation ** 
_TODO_ might be good to break up the first big from the problem statement
The best way to validate or invalidate a hypothesis is to
try it on a subset of your users. Your users are in production. That's where you
run your experiments and A/B tests. Same stuff applies to your services. The
best way to find out if that optimization actually works is by trying it on a
small subset of your requests.

This can be done very well in code, and in fact this is how Flickr does things,
or at least last I heard - using $['cfg']['some_new_feature_on'] = .01; all the
way through 1.0. This is good because the same code/configuration is running on
all the servers, so noone is wondering why graphs for this one server look
different suddenly. On the flip side, it's much harder to observe and compare
the effect - you don't really have an easy notion of a "control."

You can do the same thing by deploying a change to subset of your servers and
achieve a better observability, but now you have that other problem - folks that
aren't involved in the experiment get spooked.

Don't get mad at your engineer for `scp`ing jars to random servers in
production. I mean sure, be a little mad - you just spent an hour figuring out
why a service had been restarting on one of the boxes.. You started looking for
traces of crashes in the logs, checking error rates, trying to run smoke tests..
Only to find that someone was just deliberately restarting it. But think about
why they're doing that. *They're just getting shit done!*

![lloyd](lloyd.jpg)

** People fiddle with things in production because they're just trying to get
shit done. This is good. That's what they should be doing. **

=====

So what if we just assumed that drift was a fact of life? In fact, what if w
eallowed for a second that drift was healthy?

** Aside ** _TODO_ not sure exactly where the best place for this is yet.
Proponents of the Immutable Server pattern like to draw the analogy to a living
body's ability to destroy old cells and replace them with new cells.

I dig that. But what if the real metaphor is to be found at a higher level -
ecosystems which have a way of promoting a desirable mutation from a small
subset to the entire population and suppressing undesirable ones?

** What even IS drift? **

Drift is usually a small set of differences. A bump on a massive surface area.
I dare you to come up with a better metaphor than shaving a yak. Here's this big
hairy yak. Somewhere on this yak is a pimple. Go find it.

** Drift is difficult to find. **

But not for a computer!

Turns out computers are excellent at dealing with piles of structured
data, and ARE THEMSELVES piles of structured data.

Package lists, service lists, sysctl values, bios settings..

YES even Varnish configs!.. if you work hard enough


** Drift is meaningless without a baseline **

But baselines are all around you. The roles/clusters/runlists in your __inser
your CD tool here__. "How things were yesterday."

_TODO_ expand

** Drift is meaningless without context **

* When did it drift?            |
* What drifted?                 | WHY?
* What else was happening?      |
* Who was online?               |

Computers are not as good at figuring out the "why" but they're pretty good at
figuring out who might know.

** But why am I talkinga bout drift at a monitoring event? **

** Monitoring is the answer **

Control can come from limiting the possibilities of what can be done, or it can
come from having reliable knowledge of what has been done and why.

* _TODO_: Immutable Server also accomplishes the latter; does that need to be
addressed?
* _TODO_: need to actually introduce the notion of control (as the thing
operators/developers actually want in their infrastructure)
* _TODO_: this can probably be edited to be more powerful/pithy.

Restrictions and arcane workflows are antithetic to GST. 

Letting people do what they need to do and creating an environment where it's ok
and transparent GETS SHIT DONE.

* Audit trail, temporal context
* Easy navigation, searchability. **ACCESS**
* Fitting within the big picture (e.g. outside sources)
* Minimize surprises
* Obviate dumb fact finding missions
* Obviate sleuthing. Also, obviate hiding!

Embrace the beast; restore the trust.

** So why is context so important? **

Insert all the cognitive overhead, "programming ape" stuff here.
