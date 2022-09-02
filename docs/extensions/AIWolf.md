# World
Since there is no spacial component to the game, there are no scopes and the World has a size of (0, 0, 0).

A NLP World may be created for manipulating scentences and translating the protocol into natural language and vice-versa.

# Entities
Since there is no spacial aspect to the simulation, there are no Entities.

# Managers

## Players

### Villager
Is the only one who may reveal their role without risk.
May only vote.
Wins if humans win.

### Seer
Upon revealing role, may become subject to an attack.
May vote and divine.
Wins if humans win.

### Medium
Upon revealing role, may become subject to an attack.
May vote, has species identified upon death.
Wins if humans win.

### Bodyguard
Upon revealing role, may become subject to an attack.
May vote and guard.
Wins if humans win.

### Possessed
Upon revealing role, may become discredited (will not be believed in future).
May only vote.
Wins if warewolfs win.

### Warewolf
Upon revealing role, will likely lose to a vote.
May vote, attack and communicate with other wolves in secret.
Wins if warewolfs win.

# Actions


FIXME:
# Protocol
## Words
- Subject: ID, UNSPEC, ANY
- Target: ID, ANY
- Role: VILLAGER, SEER, MEDIUM, BODYGUARD, WAREWOLF, POSSESSED, ANY
- Species: HUMAN, WAREWOLF, ANY
- Talk number: DAY+TALK_ID
- Verb: any of the following
  1. ESTIMATE / COMINGOUT
  2. DIVINATION / GUARD / VOTE / ATTACK
  3. DIVINED / IDENTIFIED
  4. GUARDED / VOTED / ATTACKED
  5. AGREE / DISAGREE
  6. OVER / SKIP
  7. REQUEST / INQUIRE
  8. BECAUSE
  9. DAY
  10. NOT / AND / OR / XOR

## Sentences
Sentences consist of the verbs 1 - 6 with their appropriate parameters:
1. Subject Verb Target Role
2. Subject Verb Target
3. Subject Verb Target Species
4. Subject Verb Target
5. Subject Verb Talk number
6. Verb
   
## Operators