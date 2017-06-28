# How to build a bridge to buildbot
## AKA BBB

---

# BBB In a Nutshell

* Schedule task in TC
* Run job in BB
* Report results to TC
* Synchronize task/job statuses

---

# History
* 0.x Initial Prototype
* 1.x Production
* 2.x Async Python 3.5

---

# Services

- TC Listener
 - pending |
   - create BB job
   - scopes
 - exception |
   - dedaline
   - canceled

- BB Listener |
  - started |
    - claimTask()
  - finished |
    - resolveTask()
    - log upload


- Reflector |
 - reclaimTask() |
 - Async! |

---

# Consumers

* Releasetasks
* Backfill
* ???

---

# Issues

* Duplicates
* Bottlenecks
** DB Locks
** Slow DB queries
** Synchronous reflector
* No artifacts

---

# HOWTO

* Create a builder in BB
* Schedule in TC
* payload.properties

---

# Thank you!
