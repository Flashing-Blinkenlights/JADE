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
Wins if waerewolfs win.

### Werewolf
Upon revealing role, will likely lose to a vote.
May vote, attack and communicate with other wolves in secret.
Wins if werewolfs win.

# Actions


FIXME:
# Protocol
## Words
- Subject: ID, UNSPEC, ANY
- Target: ID, ANY
- Role: VILLAGER, SEER, MEDIUM, BODYGUARD, WEREWOLF, POSSESSED, ANY
- Species: HUMAN, WEREWOLF, ANY
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

# Logic for Agent (REMOVE FROM FINAL DOCUMENT)

## General
1. The safest option for all players is to out as a VILLAGER
2. Once there are fewer Possible VILLAGERs than, well, possible VILLAGERs, then every Possible VILLAGER becomes a Probable VILLAGER
3. There must be at least one WEREWOLF and one HUMAN at any point in time (otherwise the game would have ended)
4. Players that say they did an action they should not be capable of are questioned
   1. If they come out with a different role, and have not come out as a non-VILLAGER before, then they gain trust and are a Probable of the new role
   2. If they come out with a different role, and have come out as a non-VILLAGER before, then they lose trust and are a Probable WEREWOLF
   3. If they do not respond, or maintain their incorrect role, they lose trust and are a Possible WEREWOLF
5. Players that died from an attack are a Certain HUMAN

## Trust
1. Trust is a measure of how reliable a player is as a source of information
2. Trust towards all players starts at 1 and cannot go below 0
3. The following levels of trust are distinguished:
   1. 0: Untrusted, and all statements are ignored.
   2. 0.5: Dubious, considered quite unreliable
   3. 1: Tolerable, in a neutral position
   4. 1.5: Trusted, considered reliable
4. Players gain/lose 10% of their trust when they gain/lose trust, this means:
   1. Randomness will tend toward 0 over time
   2. Consecutive gains are rewarded more than intermittant gains
   3. Redemption is always possible unless trust is set to 0
5. Certain WEREWOLFs automatically have a trust of 0 (unless aligned with WEREWOLF)
6. Certain HUMANs have a trust of no less than 1
7. Certain HUMANs with special, pro-HUMAN roles have a trust of no less than 1.5
8. The most trusted players are likely HUMAN
9. The least trusted players are likely WEREWOLF or POSSESSED

## Evidence
1. There are four levels of evidence (a.k.a. credibility): 
   1. Indisputable: Publicly known truths
   2. Certain: Internally sourced evidence
   3. Probable: Supported externally sourced evidence
   4. Possible: Tentative externally sourced evidence
   5. Disregarded: Exceedingly unlikely or false statements
2. Who said what when, as well as statements from the Referee, are Indisputable evidence
3. Internally sourced information is always Certain
4. Externally sourced infromation may be at most Probable
5. All novel statements made by others are Possible
6. Players gain/lose trust when their statements gain/lose credibility
7. Initially, all externally sourced evidence is Possible
8. If there is a discrepancy between evidences, the discrepancy is noted
9.  If there is a discrepancy between evidences, the more credible evidence wins and the other evidence is Disregarded
10. If there is a discrepancy between evidences on the same level, the more trusted source's statement is considered 'truer'

## Outings
1. If someone outs themselves as a VILLAGER, they are a Possible ANY
2. If someone outs themselves as a SEER, MEDIUM or BODYGUARD, they are a Possible of that role XOR VILLAGER XOR WEREWOLF (but not of other special roles)
3. If someone outs themselves as a SEER, MEDIUM or BODYGUARD, there can only be one of that role and I am that role, then they lose trust and are a Probable VILLAGER XOR WEREWOLF
4. If someone outs themselves as a WEREWOLF or POSSESSED, they lose trust
5. If more of a given role out themselves then is possible (ignoring VILLAGER), all players identifying with that role lose trust

## Divination
1. The least trusted individuals should be divined first
2. If the result is a WEREWOLF, they are a Certain WEREWOLF and have zero trust
3. If the result is a HUMAN, they are a Certain HUMAN and gain trust

## Medeating
1. The effects of the first player to vote for the winner of the vote is given a boost, even if they change their mind
2. If a WEREWOLF was killed, then all who voted against them gain trust and all who voted differently, or defended them, lose trust
3. If a SEER, MEDIUM or BODYGUARD was killed, then all who voted against them lose trust
4. If a HUMAN was killed, then all who voted differently, or defended them, gain trust

## Guarding
1. The player with the highest trust should be guarded
2. If there was an attempted attack on the guarded player, they gain trust and, if there is only one GUARD, are a Certain HUMAN
3. If a different player was attacked and killed, the guarded player loses trust
4. If a player claiming to be a GUARD prevents an attack, gain trust and they are a Probable GUARD
5. If a player claiming to be a GUARD always guards the wrong target, lose trust

## Voting
1. If there is a Certain WEREWOLF, there is a confident vote against the WEREWOLF
2. If there is a priority target, there is a confident vote against that target
3. If there is no confident vote, the most trusted vote should be voted
4. All who vote the same as myself gain trust
5. All who criticise my vote lose trust
6. All who vote against me lose trust (unless if WEREWOLF)
7. After all have voted, if it was an unconfident vote, the new most trusted vote is voted (since knowledge of all votes is now available)

## Attacking
1. HUMANs associated with special pro-HUMAN roles are always a priority target
2. If there is a GUARD, avoid attacking the player most likely to be protected
3. If there are no priority targets, attack the second-most trusted HUMAN
4. If there is a disagreement, side with the vote targeting most trusted HUMAN
5. If a WEREWOLF targets a WEREWOLF, try to eliminate them at daytime
6. If pretending to be a GUARD as a WEREWOLF, ensure the guarded individual is not attacked

## Disclaiming Actions
1. If role has been disclosed, always disclaim correctly
2. If pretending to be a SEER,
   1. If not requested, say the closest to average trusted, that hasn't been checked previously, is a HUMAN
   2. If requested, if the target has low trust and it is possivle, claim that they are a WEREWOLF, otherwise HUMAN
   3. If there is a rival SEER,
      1. If they have a high trust, back down and claim being a VILLAGER
      2. If they have a low trust, immediately claim they are a WEREWOLF
3. If pretending to be a MEDIUM,
   1. If the deceased was a victom, always claim they were HUMAN
   2. If the deceased was eliminated, if they have low trust and it is possible, claim that they are a WEREWOLF, otherwise HUMAN
   3. If there is a rival MEDIUM, and the deceased was eliminated, copy their claim
4. If pretending to be a GUARD, 
   1. If not requested, claim to have guarded the most trusted surviving player 
   2. If requested to disclaim for the following night, pretend to guard the third most trusted Player
   3. If requested to protect a target, agree
      1. If target is killed, claim to have guarded the most trusted surviving player (in the hopes of saving two lives)

## Dis-/Agreeing
1. If an inquiry is made that requires a yes-or-no answer, respond according to evidence
2. If a statement aligns with evidence, agree and they gain trust
3. If there is a discrepancy between a statement and evidence, disagree with a reason pointing out the discrepancy and they lose trust
4. If the reason for a discrepancy is Indisputable evidence, they have zero trust 
5. If somebody else agrees with a statement I agree with before I stated my agreement, they also gain trust and my agreement will include their statement
6. If somebody else disagrees with a statement I disagree with before I have stated my disagreement, check their disagreement for a reason
   1. If there is no reason, they gain trust and I will agree with them, with a reason
   2. If there is a reason that is identical to my reason, I will agree with them
   3. If there is a reason that I agree with, but is different to my reason, I will agree with them and elaborate
   4. If there is a reason that I disagree with, I will disagree with both and provide reasons for both
7. If somebody else agrees with a statement I disagree with, or vice-versa, disagree and they lose trust

## Talking
1. If there is no other comment to say in the first round, claim the player that has the most significant (lack of) trust and 1 is a WEREWOLF or HUMAN respectively
2. If a known SEER or MEDIUM, disclaim at the soonest opportunity
3. If the victim was a suspected WEREWOLF, reevaluate evidence and communicate conclusions / newly Probable evidence

## Requesting
1. If nobody has requested divination, and there is nothing else to say, request for the least trusted player to be divinated
2. If nobody has requested guarding, and there is nothing else to say, request for the most trusted player to be guarded
3. If there is a confident vote, request that all others vote the same

## Inquiring
1. If a SEER or MEDIUM has been outed, and they have not reported their findings in the first round, inquire on their findings of past, undisclosed rounds
2. If multiple conflicting statements

## As a WEREWOLF
1. Determine a cover for all WEREWOLFs, and record those roles as Certain
   1. Inquire their role
      1. If there is no response or the response is WEREWOLF or POSSESSED, request VILLAGER (avoiding duplicate roles)
   2. If requests are made,
      1. If it is WEREWOLF of POSSESSED, out as VILLAGER
      2. If the request is valid, adopt it
   3. If no requests are made, out as VILLAGER
2. Attack according to the logic above
3. If a Probable SEER has determined a WEREWOLF, then they become a Probable WEREWOLF XOR their false role (making them eligible for a vote)
4. If accused of being a WEREWOLF,
   1. Increase trust of accuser
   2. If a reason is provided,
      1. If the reason is incorrect, disagree and correct
      2. If the reason is correct,
         1. If the reason is that they are a SEER, then they are a Probable SEER, continue as "if no reason is provided"
         2. ???
         3. If the reason is an indisputable discrepancy, request other's agreement,  *Does anyone actually believe this?*
            1. If number of positive HUMAN responses is the number of WEREWOLFs, accuse them of being WEREWOLFs, using as reason *Don't you all think it's a funny coincident that the number of people who agree is very similar to the number of werewolfs remaining?*
            2. If minority agrees, insinuate being a WEREWOLF, use as reason and disclaim that they won't be voted against *More than half of us agree that your logic is flawed, so either you're mistaken, or you are, in fact, a WEREWOLF! I'm going to give you the benefit of the doubt and say that mistakes happen, so I won't vote against you... not today, at least.*
            3. If majority agrees, out as a POSSESSED *Alright, I'll admit it, I'm a POSSESSED, so go ahead and kill me. I'll gladly sacrifice myself in the place of a WEREWOLF!*
   3. If no reason is provided,
      1. If they are a Probable SEER,
         1. Increase trust of accuser
         2. Inquire to the others whether they agree they are a SEER, *Does anyone else think ### is a SEER?*
            1. If number of positive HUMAN responses is the number of WEREWOLFs, accuse them of being WEREWOLFs, using as reason *Don't you all think it's a funny coincident that the number of people who agree is very similar to the number of werewolfs remaining?*
            2. If number of positive responses are in the minority, accuse of being a VILLAGER XOR WEREWOLF, use as reason and disclaim that they won't be voted against *More than half of us agree that you're not a SEER, so either you're a clever VILLAGER, or a WEREWOLF. I'm going to give you the benefit of the doubt and say you're a VILLAGER, so I won't vote against you... not today, at least.*
            3. If number of positive responses are in the majority, continue at "if all else fails" *If you really want to get rid of me, I won't stand in your way, but you should know that I think ### is actually a WEREWOLF.*
      2. Otherwise, inquire whether they are a SEER,
         1. If there is no response or they disagree, use as proof for invalid accusation
         2. If they agree, they are a Probable SEER, continue as "if no reason is provided"
   4. If all else fails, claim the least trusted HUMAN to be a WEREWOLF
      1. If questioned,
         1. Increase trust of questioner
         2. If accused voted for the elimination of HUMANs,
            1. If WEREWOLF not pretending to be MEDIUM or disclosed all required eliminations,
               1. List all the times the accused voted against HUMANS
                  1. If questioned,
                     1. Increase trust of questioner
                     2. If no MEDIUM has been exposed and pretending to be VILLAGER,
                        1. Out as MEDIUM, and use as reason
                           1. If other MEDIUM outs or disagrees, repeat "if accused of being a WEREWOLF"
                     3. Otherwise, do not respond (and hope for the best)
5. If being voted for elimination,
   1. Increase trust of all voting for me
   2. If pretending to be VILLAGER, received largest or second-largest vote and survived,
      1. If nobody has outed as SEER, MEDIUM or GUARD, out as that role (preferably MEDIUM or GUARD)
      2. Otherwise out as POSSESSED *Yesterday I was nearly eliminated anyway, I might as well *

# As a POSSESSED
Act identically to a WEREWOLF, but without whispers or attacks.

# As a VILLAGER
1. Out as a VILLAGER
2. As soon as somebody outs as a pro-HUMAN special role, act and out as that role
