# CodeReminder

Brett Terpstra 2015 <http://brettterpstra.com>

MIT License <http://choosealicense.com/licenses/mit/>

A CLI to add a Reminders.app reminder and/or OmniFocus task so you don't forget about that repo you cloned to play with later.

## Usage

    cremind [-r] [-t] [-n NOTE] [path]

        -r, --reminder                   Create a Reminders.app reminder
        -t, --task                       Create an OmniFocus task
        -n, --note NOTE                  Add a note
        -h, --help                       Display this screen

Both `-r` and `-t` options can be provided, if neither is given it will default to the `default_type` option (see Configuration).

If an existing path is provided at the end of the command, it will be used, otherwise, cremind will default to the current working directory.

The title of the task or reminder will always be the basename of the path, and
the full path will be the first line of the attached note. If an additional (-n
"NOTE") flag is provided, "NOTE" will be appended.

## Installation 

1. Copy the `cremind` script to a location in your $PATH. 
2. Make it executable with `chmod a+x /path/to/cremind`

## Configuration

Edit the configuration options at the top of the script.

**of_project**

_Default: "Code Reminders"_

The name of OmniFocus project to add tasks to. Project can be nested in folders. If a project with the specified name doesn't exist, it will be created in the root of the OmniFocus document.

**reminders_list**

_Default: "Code Reminders"_

The name of the Reminders.app list to use. If it doesn't exist, it will be created.

**default_type**

_Default: "reminder"_

If neither -r or -t options are provided, default to this type. The value should be a quoted string, either "reminder" or "task".
