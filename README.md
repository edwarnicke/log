log is a simple logrus helper to allow attaching a [logrus.Entry](https://godoc.org/github.com/sirupsen/logrus#Entry)
to a [context.Context](https://golang.org/pkg/context/#Context).

```go
// Create a ctx that carries a logrus.Entry with field "cmd" indicating the executable being run
ctx := log.WithField(ctx, "cmd", os.Args[0])
ctx = log.WithFields(ctx,WithFields(parent, 
            logrus.Fields{
                "pid": os.Getpid(),
                "uid": os.Getuid(),
            },
       )
log.Entry(ctx).Info("Informational log")
```
