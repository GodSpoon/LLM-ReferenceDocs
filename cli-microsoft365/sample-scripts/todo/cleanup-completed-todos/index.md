-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
tags:
  - cleanup
  - tasks
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Cleanup completed Microsoft To Do tasks

Author: [Garry Trinder](https://garrytrinder.github.io/2021/04/EXAMPLE_SECRET_VALUE_PLACEHOLDER)

Microsoft To Do is my task management tool of choice, I use it for tracking everything I do, which means I generate and complete a lot of tasks during a working week.

This script iterates across all of the task lists and removes the tasks that have been marked as complete.

<Tabs>
  <TabItem value="PowerShell">

  ```powershell
  Write-Output "Getting Microsoft To Do task lists ..."
  $lists = m365 todo list list -o json | ConvertFrom-Json

  Write-Output "Iterating Microsoft To Do task lists ..."
  $lists | ForEach-Object { 
      $listId = $_.Id
      
      Write-Output "Getting completed tasks from '$($_.displayName)' task list ..."
      $tasks = m365 todo task list --listId $listId -o json --query '[?status==`completed`]' | ConvertFrom-Json
      Write-Output "$($tasks.Count) completed tasks found ..."

      $tasks | ForEach-Object {
          Write-Output "Removing '$($_.Title)' task ..."
          m365 todo task remove --listId $listId --id $_.Id --force
      }
  }

  Write-Output "Done"
  ```

  </TabItem>
  <TabItem value="Bash">

  ```bash
  #!/usr/bin/env bash
  # -*- coding: utf-8 -*- 

  echo "Getting Microsoft To Do task lists ..."
  strListIds=`m365 todo list list --query '[].id'`
  arrListIds=($strListIds)

  echo "Iterating Microsoft To Do task lists ..."
  for strlistId in "${arrListIds[@]}"; do
      echo "Getting completed tasks from '${strlistId}' task list ..."
      strTaskIds=$(m365 todo task list --listId "${strlistId}" --query '[?status==`completed`].id')
      arrTaskIds=($strTaskIds)
      strCount=${#arrTaskIds[@]}
      echo "${strCount} completed tasks found ..."    
      for strTaskId in "${arrTaskIds[@]}"; do
          echo "Removing '${strTaskId}' task ..."
          m365 todo task remove --listId "${strlistId}" --id "$strTaskId" --force
      done
  done

  echo "Done"
  ```

  </TabItem>
</Tabs>
