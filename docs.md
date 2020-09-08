# PLAYER TAGGING DOCUMENTATION

> The idea is to have a table that records data in this format:

| Player   | Event          | Type/ Location | Outcome | Start time | End Time | 
| -------- | -------------- | -------------- | ------- | ---------- | -------- |


    EVENTS PANEL 
    EVENT - TYPE/LOCATION - OUTCOME

    PASS - LONG/LINEBREAK/SHORT - SUCCESSFUL/UNSUCCESSFUL
    DRIBBLE - NUTMEG/SKILLMOVE - SUCCESSFUL/UNSUCCESSFULL
    SHOT - LONGRANGE/SHORTRANGE - SUCCESSFUL/UNSUCCESSFUL
    CROSS - NONE - SUCCESSFUL/UNSUCCESSFUL
    GOALS - HEADER/INSIDEBOX/OUTSIDEBOX - NONE
    ASSISTS
    FREEKICKS - NONE - LEDTOCHANCE
    PENALTIES - NONE -  MISSED/SCORED
    FOULS - OPPONENTSHALF/OWNHALF - WON/CONCEDED
    INTERCEPTIONS - OWNHALF/OPPONENTHALF - NONE
    TACKLES -  NONE - SUCCESSFUL/UNSUCCESSFUL
    BALL PROGRESSION - OWNHALF/OPPONENTSHALF - NONE
    BLOCKS - NONE - NONE
    CLEARANCE - GOALLINE/UNDERPRESSURE - NONE
    DUELS - AERIAL/GROUND - WON
    SAVES - INSIDEBOX/OUTSIDEBOX/1V1 - NONE
    CARD - DISSENT/FOUL - RED/YELLOW
      
    

### PLAYER 

    player: {
        id 
        teamId 
        name 
        age 
        position
        playerMatchEvents[]
        }

### MATCH 
    match: {
        id
        competitionId
        teamA
        teamB 
        corners
        freeKicks
        passes
        teamAPossession
        teamBPossesion
        teamAScoreLine
        teamBScoreLine
        yellowCardsTeamA
        redCardsTeamA
        yellowCardsTeamB
        redCardsTeamB
        shotsTeamA
        shotsTeamB
        shotsOnTargetTeamA
        shotsOnTargetTeamB
        }


### PLAYER EVENTS DURING MATCH
    playerMatchEvents: {
            matchId
            playerId 
            competitionId

            passes: {
                timeLine[]
                successfulLongPasses
                successfulLineBreakingPasses
                successfulShortPasses
                totalNumberOfPasses
            }
            
            dribbles : {
                timeLine[]
                successfulNutmegs
                unsuccessfulNutmegs
                successfulSkillMoves
                unsuccessfulSkillMoves
            }

            shots : {
                timeLine[]
                longRangeOffTarget
                longRangeOnTarget
                shortRangeOffTarget
                shortRangeOnTarget
            }

            crosses: {
                timeLine[]
                successful
                unsuccessful
                totalNumber
            } 

            goals: {
                timeLine[]
                headers
                1v1
                insideBox
                outsideBox
            }

            assists : timeLine[]
            chanceCreated: timeLine[]
            freeKicks: {
                timeLine[] 
                chanceCreated
            }

            penalties: {
                timeLine[]
                missed
                scored
            }

            fouls : {
                wonInOpponentsHalf
                wonInOwnHalf
                ConcededInOpponentsHalf
                ConcededInOwnHalf
            }

            interceptions: {
                timeLine[]
                opponentsHalf
                ownHalf
            }

            tackles: {
                successful 
                unsuccessful 
            }

            ballProgression: {
                timeLine[]
                ownHalf
                opponentsHalf
            }

            Blocks

            Clearance: {
                goalLine
                underPressure
            }

            Duels: {
                wonAerial
                wonGround
            }

            saves: {
                timeLine[]
                1v1
                insideBox
                outsideBox
            }

            card: {
                yellowDissent
                yellowFoul
                redFoul
                redDissent
            }

    }


### Team 

    team: {
        id
        name
        leagueid
        season
    }


### League

    league: {
        id
        name
        season
    }



