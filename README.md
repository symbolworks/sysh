# Sysh

**Symbolic shell as a unified frontend to a class of application backends**

## Motivation

In an attempt to simplify communication between users and applications, we try to reduce graphic user interface (GUI) interaction to symbolic instructions and results. We are exploring an experiment where interaction with a certain class of applications may be significantly simplified in relation to common GUIs built on top of those applications.

Considering the current context within an application, symbolic instructions may be gradually discovered instead of memorizing the entire application instruction set. Being of symbolic nature, application instructions gain a lot of positive features like simplicity, portability, scriptability, and reproducibility.

Because symbolic input/output preferably carry only necessary communication information, when working with an application, there are less distractions in the form of notifications, sounds, images, videos, etc. Hopefully, only information related to work of interest remains.

This reduced user interface platform is not a replacement to usual GUIs because there are still a lot of applications that work better with graphic environments. But we also may acknowledge that there exists a considerable range of applications that would benefit from a short and concise set of common instructions exchanged between user and computer.

## Unified Frontend

Modern programming taught us about the importance of separating frontend from backend in building computer applications. While backend internals are a matter of completely another material, we question how much the frontend creation can be automated. Frontend communicates with backend using application programming interface (API), so the API is one of the first places to look at when analyzing the frontend.

Frontend GUIs may grow very complex, but how much machinery is actually necessary to interact with useful software? Applications like CAD, photo editing, video editing, music arrangement, games, diagrams, scientific visualization, some spreadsheets, etc., greatly benefit from spatial representation on the screen, so we may expect that they already use an effective communication channel. On the other hand, for applications like calendar, contacts, mail, notes, tasks, configuration, databases, etc., there exists an argument that a visual canvas is too broad abstraction. Their communication channel resembles conceptual symbolic interaction, and may be a subject of automating its appearance to users.

With applications whose primary communication channel resembles conceptual symbolic interaction, we may introduce a simple but universal self-describing API that would enable creation of a unified frontend client. Such a frontend client wouldn't need to be aware of the backend specifics, yet it would be able to meaningfully interact with any standardized backend. The proposed frontend client would expose its functionality using the following repetitive pattern:

```
Context -> Discover -> Choose -> Execute -> New Context
```

The pattern may embrace a surprisingly capable class of the above mentioned applications, providing the unified frontend client whose functionality would depend merely on standardized metadata passed within API calls. Since the frontend could be aware of the current context sensitive set of instructions, it could successfully mediate interaction between end user and the whole application. The application's API instructions can correspond directly to user-level instructions, making the API itself the primary interaction mechanism.

All of this leads us to a definition of potentially simplistic unified frontend, which may, in turn, unify access to the entire class of applications. For such applications, programmers could build an application backend without developing an application-specific frontend. Consequently, all those applications would share a common command line discoverable input/output interface, letting the user to further learn about application specific instructions.

## Example Session

When the UI starts, we see:

```
Welcome. Choose an application command:

    email
    tasks
    notes

    done
```

We write `tasks`. UI responds:

```
Tasks. Choose a command:

    task-list
    new-task
    edit-task
    delete-task
    move-task

    done
```

We write `new-task`. UI responds:

```
task date and time:
```

We write: `"08/09/2026., 10:00am"`. UI responds:

```
task description:
```

We write `"go to dentist"`. UI responds:

```
08/09/2026., 10:00am - go to dentist

Task created. Choose a command:

    next-task

    done
```

We write: `done`. We're back to the tasks menu:

```
Tasks. Choose a command:

    task-list
    new-task
    edit-task
    delete-task
    move-task

    done
```

We write: `done`. We're back to the applications menu:

```
Welcome. Choose an application command:

    email
    tasks
    notes

    done
```

We write `done`. The session ends.
