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
- 0.x Initial Prototype |
- 1.x Production        |
  - 3 services          |
  - Multihomed          |
- 2.x Async Python 3.5  |

---

# 3 Services

---
# TC Listener
- pending         |
  - create BB job |
  - scopes        |
- exception       |
  - deadline      |
  - canceled      |

---

# BB Listener
- started         |
  - claimTask()   |
- finished        |
  - resolveTask() |
  - log upload    |

---

# Reflector
- reclaimTask() |
- Async!        |

---
# Limitations

- Requires BB builder        |
- Properties all the things! |
- Artifacts                  |

---
# Issues

- Duplicates              |
- Bottlenecks             |
  - DB Locks              |
  - Slow DB queries       |
  - Synchronous reflector |

---
# Consumers

- Releasetasks
- Backfill
- ???

---

# HOWTO

* Create a builder in BB |
* Schedule in TC         |
* payload.properties     |

---

# Thank you!
