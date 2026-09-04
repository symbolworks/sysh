# Sysh

**Symbolic shell as a unified frontend to a class of application backends**

## Motivation

In an attempt to simplify communication between users and applications, we try to reduce graphic user interface (GUI) interaction to symbolic instructions and results. We are exploring an experiment where interaction with a certain class of applications may be significantly simplified in relation to common GUIs built on top of those applications.

Considering the current context within an application, symbolic instructions may be gradually discovered instead of memorizing the entire application instruction set. Being of symbolic nature, application instructions gain a lot of positive features like simplicity, portability, scriptability, and reproducibility.

Because symbolic input/output preferably carry only necessary communication information, when working with an application, there are less distractions in the form of notifications, sounds, images, videos, etc. Hopefully, only information related to work of interest remains.

This reduced user interface platform is not a replacement to usual GUIs because there are still a lot of applications that work better with graphic environments. But we may also acknowledge that there exists a considerable range of applications that would benefit from a short and concise set of common instructions exchanged between user and computer.

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
