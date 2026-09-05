# Sysh

**Symbolic shell as a unified frontend to a class of application backends**

## Motivation

In an attempt to simplify communication between users and applications, we try to reduce graphic user interface (GUI) interaction to symbolic instructions and results. We are exploring an experiment where interaction with a certain class of applications may be significantly simplified in relation to common GUIs built on top of those applications.

Considering the current context within an application, symbolic instructions may be gradually discovered instead of memorizing the entire application instruction set. Being of symbolic nature, application instructions gain a lot of positive features like simplicity, portability, scriptability, and reproducibility.

Because symbolic input/output preferably carry only necessary communication information, when working with an application, there are less distractions in a form of notifications, sounds, images, videos, etc. Hopefully, only information related to work of interest remains.

This reduced user interface platform is not a replacement to usual GUIs because there are still a lot of applications that work better with graphic environments. But we may also acknowledge that there exists a considerable range of applications that would benefit from a short and concise set of simple instructions exchanged between user and computer.

## Example Session

When the session starts, user interface (UI) shows:

```
Welcome. Choose an application command:

    tasks
    notes
    calc

    done

>
```

We write `tasks` and press [enter]. UI responds:

```
Tasks. Choose a command:

    task-list
    new-task
    edit-task
    delete-task
    move-task

    done

tasks>
```

We enter `new-task`. UI responds:

```
New task. Date and time:

   <string [DD/MM/YYYY, HH:MM]>
   
   cancel

tasks/new-task>
```

We enter `"08/09/2026, 10:00"`. UI responds:

```
New task. Description:

    <string>
    
    cancel

tasks/new-task>
```

We enter `"Go to dentist"`. UI responds:

```
Task created.
    
    date and time: "08/09/2026, 10:00"
    description:   "Go to dentist"

Tasks. Choose a command:

    task-list
    new-task
    edit-task
    delete-task
    move-task

    done

tasks>
```

We enter `done`. We're back to the applications menu:

```
Welcome. Choose an application command:

    tasks
    notes
    calc

    done

>
```

We enter `done`. The session ends.
