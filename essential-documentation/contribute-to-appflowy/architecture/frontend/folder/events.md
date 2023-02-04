# Events

Events are used in the [communication](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/architecture/frontend/inter-process-communication) between the frontend and the backend.
If you interested in the process about generating the events files, please check [this](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/architecture/backend/event) out. 
This document explains the events defined in the Folder scope.


| FolderEvent          |                                                                   |
|----------------------|-------------------------------------------------------------------|
| CreateWorkspace      | Create a new workspace                                            |
| ReadCurrentWorkspace | Read the current opening workspace                                |
| OpenWorkspace        | Open the workspace and mark it as the current workspace           |
| ReadWorkspaceApps    | Return a list of apps that belong to this workspace               |
| CreateApp            | Create a new app                                                  |
| DeleteApp            | Delete the app                                                    |
| ReadApp              | Return the app info                                               |
| UpdateApp            | Update the app's properties including the name,description, etc.  |
| CreateView           | Create a new view in the corresponding app                        |
| ReadView             | Return the view info                                              |
| UpdateView           | Update the view's properties including the name,description, etc. |
| DeleteView           | Move the view to the trash folder                                 |
| DuplicateView        | Duplicate the view                                                |
| CloseView            | Close and release the resources that are used by this view        |
| SetLatestView        | Set the current visiting view                                     |
| MoveItem             | Move the view or app to another place                             |
| ReadTrash            | Read the trash that was deleted by the user                       |
| PutbackTrash         | Put back the trash to the origin folder                           |
| DeleteTrash          | Delete the trash from the disk                                    |
| RestoreAllTrash      | Put back all the trash to its original folder                     |
| DeleteAllTrash       | Delete all the trash from the disk                                |

