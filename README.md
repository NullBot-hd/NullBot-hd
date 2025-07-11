# Hi I'm NullBot

- ## Lua Projects
  >### [Prop Hunt Game](https://www.roblox.com/games/15770783003/Game)
    **Project Status:** Work in Progress (Since Dec 2023)

    A school project for my A levels, which originally starting as a passion project.

    The game is a fast-paced, multiplayer Prop Hunt game built within Roblox Studio.
    
    Inspired by [Midnight Ghost Hunt](https://store.steampowered.com/app/915810/Midnight_Ghost_Hunt/)

    <img src="images/Networking_PropHunt.png" height="50%" width="50%" alt="Networking"/>

    ### Key Features

    - ## **Currently working on**
      
        Custom implenetation of the A* Algorithm

        https://github.com/user-attachments/assets/1e257109-5145-472f-a095-1c25180e46c2

        https://github.com/user-attachments/assets/4a57f24c-1fd9-4635-84cc-32920e0c3562

        ``` Luau
        function AStarAlgorithm(startNode, targetNode)

            local openList = {}
            local closedList = {}
        
            local currentNode = nil
        
            openList[#openList + 1] = {["Node"] = startNode, ["G"] = 0 ,["F"] = calculateDistance(startNode.EntryPoint1.Position, targetNode.EntryPoint1.Position)}
        
            while #openList > 0 do
    
                table.sort(openList, function(a, b)
                  return a.F < b.F
                end)
          
                currentNode = openList[1]
                closedList[#closedList + 1] = openList[1]
                table.remove(openList, 1)
        
                if closedList[#closedList].Node == targetNode then
                    print("Found path")
                    --print(closedList)
                    return closedList
                end
    
           
                for i, v in _G.graph[currentNode.Node] do
        
                    local isInList = false
                    for _, closedListV in ipairs(closedList) do
                        if closedListV.Node == v.Node then
                            isInList = true
                            break
                        end
                    end
        
                    for _, openListV in ipairs(openList) do
                        if openListV.Node == v.Node then
                            isInList = true
                            break
                        end
                    end
        
                    if isInList then
                        continue
                    end
        
                    local isInOpenList = false
                   	openList[#openList + 1] = {["Node"] = v.Node, ["G"] = currentNode.G + v.Length, ["F"] = currentNode.G + v.Length + calculateDistance(v.AccessPoint.Position, targetNode.EntryPoint1.Position)}
                end 
        
                task.wait()
            end
  
          return nil
        end
        ```




    - ## **Interactive UI/UX:**

        https://github.com/user-attachments/assets/bf4a2dca-aec4-4cb2-8e1f-1eac82ddc1f0

    - ## **Map Selection:**

        ![Map Selection](https://github.com/user-attachments/assets/62126cab-422e-499c-a693-4d69347fd1d7)

    - ## **Robust and Fast Prop Transformation System:**

        https://github.com/user-attachments/assets/444c99f7-53ef-4e49-9230-3058e5d3b905



  - ## **Custom Prop Movement:**
      
      https://github.com/user-attachments/assets/09fd8f24-6667-4285-a3ad-2feb9b09a976

      https://github.com/user-attachments/assets/377ff1dd-01d1-4d3e-8400-727b8b7825c7

      https://github.com/user-attachments/assets/ff2542e5-0ddb-4965-aabc-03c6923d2631


  - ## **Server & Client Replication**
 
    https://github.com/user-attachments/assets/32d12776-570d-4cab-8978-35265c2fd6f4

    https://github.com/user-attachments/assets/f87d5d96-634e-4467-a9d7-6798b207121e
