//: Playground - noun: a place where people can play

import UIKit




// Soocer League

/*
 Manually create a single collection named 'players' that contains all information for all 18 players. Each player must themselves be represented by a Dictionary with String keys and the corresponding values.
 */

// Each player has their own dictionary
typealias player = [String : Any]
typealias playerArray = [player]

let player1: player = [
    "name": "Joe Smith",
    "height": 42,
    "experience": true,
    "guardian": "Jim and Jan Smith"
]

let player2: player = [
    "name": "Jill Tanner",
    "height": 36,
    "experience": true,
    "guardian": "Clara Tanner"
]

let player3: player = [
    "name": "Billy Bon",
    "height": 43,
    "experience": true,
    "guardian": "Sara and Jenny Bon"
]

let player4: player = [
    "name": "Eva Gordon",
    "height": 45,
    "experience": false,
    "guardian": "Wendy and Mike Gordon"
]

let player5: player = [
    "name": "Matt Gill",
    "height": 40,
    "experience": false,
    "guardian": "Charles and Sylvia Gill"
]

let player6: player = [
    "name": "Kimmy Stein",
    "height": 41,
    "experience": false,
    "guardian": "Bill and Hilary Stein"
]

let player7: player = [
    "name": "Sammy Adams",
    "height": 45,
    "experience": false,
    "guardian": "Jeff Adams"
]

let player8: player = [
    "name": "Karl Saygan",
    "height": 42,
    "experience": true,
    "guardian": "Heather Bledsoe"
]

let player9: player = [
    "name": "Suzane Greenberg",
    "height": 44,
    "experience": true,
    "guardians": "Henrietta Dumas"
]

let player10: player = [
    "name": "Sal Dali",
    "height": 41,
    "experience": false,
    "guardian": "Gala Dali"
]

let player11: player = [
    "name": "Joe Kavalier",
    "height": 39,
    "experience": false,
    "guardian": "Sam and Elaine Kavalier"
]

let player12: player = [
    "name": "Ben Finkelstein",
    "height": 44,
    "experience": false,
    "guardian": "Aaron and Jill Finkelstein"
]

let player13: player = [
    "name": "Diego Soto",
    "height": 41,
    "experience": true,
    "guardian": "Robin and Sarika Soto"
]

let player14: player = [
    "name": "Chloe Alaska",
    "height": 47,
    "experience": false,
    "guardian": "David and Jamie Alaska"
]

let player15: player = [
    "name": "Arnold Willis",
    "height": 43,
    "experience": false,
    "guardian": "Claire Willis"
]

let player16: player = [
    "name": "Phillip Helm",
    "height": 44,
    "experience": true,
    "guardian": "Thomas Helm and Eva Jones"
]

let player17: player = [
    "name": "Les Clay",
    "height": 42,
    "experience": true,
    "guardian": "Wyonna Brown"
]

let player18: player = [
    "name": "Herschel Krustofski",
    "height": 45,
    "experience": true,
    "guardian": "Hyman and Rachel Krustofski"
]

let players: playerArray = [player1, player2, player3, player4, player5, player6, player7, player8, player9, player10, player11, player12, player13, player14, player15, player16, player17, player18]

// Team names
var sharks = [[String : Any]] ()
var raptors = [[String : Any]] ()
var dragons = [[String : Any]] ()


// Part 2

// Players with experience are put into their own little box
var inExperiencedPlayers = [[String : Any]] ()
var experiencedPlayers = [[String : Any]]()

// Logic to sort players with and without experience

for player in players {
    if player ["experience"] as? Bool == true {
        experiencedPlayers.append(player)
    } else {
        inExperiencedPlayers.append(player)
    }
}


// now lets sort inexperienced players by height


var sortedInExperiencedPlayers = inExperiencedPlayers.sorted { (player1, player2) -> Bool in
    let player1Height = player1["height"] as? Double ?? 0
    let player2Height = player2["height"] as? Double ?? 0
    return player1Height < player2Height
}


// sort experienced players by height also

var sortedExperiencedPlayer = experiencedPlayers.sorted { (player1, player2) -> Bool in
    let player1Height = player1["height"] as? Double ?? 0
    let player2Height = player2["height"] as? Double ?? 0
    return player1Height < player2Height
}



// Now both groups are standing in order from shortest to tallest, I want to divede them up evenly but not sure of best way to do this

var count = experiencedPlayers.count
while count > 0 {
    sharks.append(sortedExperiencedPlayer.removeFirst())
    dragons.append(sortedExperiencedPlayer.removeFirst())
    raptors.append(sortedExperiencedPlayer.removeFirst())
    count -= 3
}
var counter = inExperiencedPlayers.count
while counter > 0 {
    sharks.append(sortedInExperiencedPlayers.removeFirst())
    dragons.append(sortedInExperiencedPlayers.removeFirst())
    raptors.append(sortedInExperiencedPlayers.removeFirst())
    counter -= 3
}

var sharksHeight: [Double] = []
var dragonsHeight: [Double] = []
var raptorsHeight: [Double] = []

var sharksAverage: Double = 0
var dragonsAverage: Double = 0
var raptorsAverage: Double = 0

var averageHeightforTeam: Double = 0
var teamsAverageHeight: Double = 0



// build logic that will collect all heights or a team and store them into an array

func heightsCollectorBy(teamHeightBox: inout[Double], teamName: [[String : Any]]) -> [Double] {
    for player in teamName {
        if let heights = player["heights"] as? Double {
            teamHeightBox.append(heights)
        }
    }
    return teamHeightBox
}

heightsCollectorBy(teamHeightBox: &dragonsHeight, teamName: dragons)
heightsCollectorBy(teamHeightBox: &sharksHeight, teamName: sharks)
heightsCollectorBy(teamHeightBox: &raptorsHeight, teamName: raptors)


// calculating average team height

func averageHeightforTeam(team: [Double]) -> Double {
    averageHeightforTeam = 0
    for playerHeights in team {
        averageHeightforTeam += playerHeights
    }
    teamsAverageHeight = averageHeightforTeam / Double(team.count)
    return teamsAverageHeight
}

raptorsAverage = averageHeightforTeam(team: raptorsHeight)
dragonsAverage = averageHeightforTeam(team: dragonsHeight)
sharksAverage = averageHeightforTeam(team: sharksHeight)

// Part 3


let practiceTimeDragons = "March 17th @ 1pm"
let practiceTimeSharks = "March 17th @ 3pm"
let practiceTimeRaptors = "March 18th @ 1pm"

let dragonsTeamName = "Dragons Soccer Team"
let sharksTeamName = "Sharks Soccer Team"
let raptorsTeamName = "Raptors Soccer Team"


for player in players {
    var guardian = player["guardian"]
    var playersName = player["name"]
    var practiceTime = "ADD PRACTICE TIME"
    
    var messageDragons = ("\n Hi \(guardian),\n\n \(playersName) has been selected to play for the Dragons! The First team practice will be at Capital Park \(practiceTimeDragons). We look forward to having \(playersName) on the team!\n\n Thanks,\n Little League Soccer Volunteers")
    var messageSharks = ("\n Hi \(guardian),\n\n \(playersName) has been selected to play for the Sharks! The First team practice will be at Capital Park \(practiceTimeSharks). We look forward to having \(playersName) on the team!\n\n Thanks,\n Little League Soccer Volunteers")
    var messageRaptors = ("\n Hi \(guardian),\n\n \(playersName) has been selected to play for the Raptors! The First team practice will be at Capital Park \(practiceTimeRaptors). We look forward to having \(playersName) on the team!\n\n Thanks,\n Little League Soccer Volunteers")
    print(messageSharks)
    print(messageDragons)
    print(messageRaptors)
}




















