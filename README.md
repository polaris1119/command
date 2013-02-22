command
=======

实现类型go命令管理功能，方便管理子命令以及输出帮助信息等

使用方法
====
    package main

    import (
        "command"
    )

    var cmdInstall = &command.Command{
        UsageLine: "install [flags] [packages]",
        Short:     "compile and install packages and dependencies",
        Long: `
    Install compiles and installs the packages named by the import paths,
    along with their dependencies.
        `,
    }

    func init() {
        cmdInstall.Run = runInstall
    }

    func main() {
        usageLine := "autogo is a useful tool that helps building go projects automatically"
        commands := []*command.Command{
            cmdInstall,
        }
        command.InitProgram(usageLine, commands)
    }

    func runInstall(cmd *command.Command, args []string) {
    }
