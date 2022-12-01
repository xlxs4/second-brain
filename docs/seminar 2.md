![[Pasted image 20221201200633.png]]

Interactive drive - persistent directory shared across all juliahub stuff, you can play with things you would. Limited in size and rigor

DataSets - structured way of referring to your data that can be larger on what can fit on a Drive. Nice, rigorous way of looking at your data. Again shared across all JuliaHub stuff

"Small" data import:
Fun trip record data for taxis in New York city:
![[Pasted image 20221201200825.png]]

Lots of files:
![[Pasted image 20221201200836.png]]

![[Pasted image 20221201201234.png]]

Now as DataSet:

Not like this!
![[Pasted image 20221201201411.png]]

this is for small data (notice it's now loaded in VSCode):
![[Pasted image 20221201201440.png]]

For big data we use the JuliaHub API through `JuliaHubClient` (TODO: Add link).
It's only available when you're running Julia inside JuliaHub:
![[Pasted image 20221201201615.png]]

`Blob`s (TODO: add gelatinous cube reference)

Gives you info on how to manually connect into this 'bucket' the data is in:
![[Pasted image 20221201201827.png]]

The creds are only scoped/only have access to this bucket of data and for this particular session.

When you're done uploading they become invalid.

You use AWS tools, e.g. the open-source `Rclone`, which has integrated support with `add Rclone_jll`:
![[Pasted image 20221201202007.png]]

It also supports various backends:
![[Pasted image 20221201202057.png]]

and more.

Creating a new credentials file for s3.
Interactively:
![[Pasted image 20221201202214.png]]

Or manually:
![[Pasted image 20221201202326.png]]

and we're in:
![[Pasted image 20221201202335.png]]

(you can change the region from the default `us-east-1`, thanks to JuliaHub)

![[Pasted image 20221201202418.png]]

if it gets interrupted and re-run it, it knows that some files were already uploaded. It's very robust:
![[Pasted image 20221201202524.png]]

It's a bit of an advanced API, but very reliable and handy

and the 45GB file is now uploaded:
![[Pasted image 20221201202623.png]]

Notice that it was marked as public, so anyone using the JuliaHub cluster, they can browse the data

DataSets are versioned, referenceable from parallel tasks. What does using Julia to play with the data look like? Parallel process:

open dataset:
![[Pasted image 20221201202839.png]]

`using DataSets`, a public Julia package. It knows where DataSets can be, and one of these remotes is JuliaHub

i.e. here (both public and private):
![[Pasted image 20221201202918.png]]

there's a copy this DataSet button
![[Pasted image 20221201202935.png]]

packages:
![[Pasted image 20221201203054.png]]

if you run this it gives you the metadata for the DataSet:
![[Pasted image 20221201203125.png]]

lazy references to the data that are there, it displays as though they are folders in a tree:
![[Pasted image 20221201203221.png]]

now accessible in my cloud computing environment

notice that they weren't downloaded
you can grab a reference to a particular file, still lazy (only a reference, haven't downloaded anything):
![[Pasted image 20221201203310.png]]

if you want to read it, you can stream it as a Julia IO device.

running in parallel across a cluster:
`@everywhere`: all workers know
