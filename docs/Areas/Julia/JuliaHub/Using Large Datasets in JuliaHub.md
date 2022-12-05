[Using Large Datasets in JuliaHub - YouTube](https://www.youtube.com/watch?v=7oOrLRk0_0Q)

Interactive drive - persistent directory shared across all juliahub stuff, you can play with things you would. Limited in size and rigor

DataSets - structured way of referring to your data that can be larger on what can fit on a Drive. Nice, rigorous way of looking at your data. Again shared across all JuliaHub stuff

"Small" data import:
Fun trip record data for taxis in New York city:

Lots of files:

Now as DataSet:

Not like this!

this is for small data (notice it's now loaded in VSCode):

For big data we use the JuliaHub API through `JuliaHubClient` (TODO: Add link).
It's only available when you're running Julia inside JuliaHub:

`Blob`s (TODO: add gelatinous cube reference)

Gives you info on how to manually connect into this 'bucket' the data is in:

The creds are only scoped/only have access to this bucket of data and for this particular session.

When you're done uploading they become invalid.

You use AWS tools, e.g. the open-source `Rclone`, which has integrated support with `add Rclone_jll`:

It also supports various backends:

and more.

Creating a new credentials file for s3.
Interactively:

Or manually:

and we're in:

(you can change the region from the default `us-east-1`, thanks to JuliaHub)


if it gets interrupted and re-run it, it knows that some files were already uploaded. It's very robust:

It's a bit of an advanced API, but very reliable and handy

and the 45GB file is now uploaded:

Notice that it was marked as public, so anyone using the JuliaHub cluster, they can browse the data

DataSets are versioned, referenceable from parallel tasks. What does using Julia to play with the data look like? Parallel process:

open dataset:

`using DataSets`, a public Julia package. It knows where DataSets can be, and one of these remotes is JuliaHub

i.e. here (both public and private):

there's a copy this DataSet button

packages:

if you run this it gives you the metadata for the DataSet:

lazy references to the data that are there, it displays as though they are folders in a tree:

now accessible in my cloud computing environment

notice that they weren't downloaded
you can grab a reference to a particular file, still lazy (only a reference, haven't downloaded anything):

if you want to read it, you can stream it as a Julia IO device.

running in parallel across a cluster:
`@everywhere`: all workers know
