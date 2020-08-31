# Chapter 7

## 7.1 Measuring A Robot
```javascript
function compareRobots(robot1, memory1, robot2, memory2) {
  const turns = 100
  let [totalRouteRobotTurns, totalGoalRobotTurns] = [0, 0]

  for (let cycles = 0; cycles < turns; cycles++) {
    const state = VillageState.random()
    totalRouteRobotTurns += countTurns(state, robot1, memory1)
    totalGoalRobotTurns += countTurns(state, robot2, memory2)
  }

  const averageRouteRobotTurns = totalRouteRobotTurns / turns
  const averageGoalRobotTurns = totalGoalRobotTurns / turns
  console.log(`Route robot on average took ${averageRouteRobotTurns} turns`)
  console.log(`Goal oriented robot on average took ${averageGoalRobotTurns} turns`)
}

function countTurns(state, robot, memory) {
  for (let turns = 0;; turns++) {
    if (state.parcels.length == 0) return turns
    let action = robot(state, memory);
    state = state.move(action.direction);
    memory = action.memory;
  }
}

compareRobots(routeRobot, [], goalOrientedRobot, []);
```

## 7.2 Robot efficiency
```javascript
function myRobot({place, parcels}, route) {
  if (route.length == 0) {
    let routes = parcels.map(parcel => {
      if (parcel.place != place) {
        return {route: findRoute(roadGraph, place, parcel.place)};
      } else {
        return {route: findRoute(roadGraph, place, parcel.address)};
      }
    })
    
    route = routes.reduce((a, b) => b.route.length < a.route.length ? a : b).route
  }
  return {direction: route[0], memory: route.slice(1)};
}
```