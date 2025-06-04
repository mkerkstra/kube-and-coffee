# Session 4: PVC You Later

An introduction to persistent storage and StatefulSets.

## Goals
* Understand PersistentVolumes, Claims and StorageClasses
* Learn why stateful workloads are special
* Explore StatefulSets and their identity guarantees

## Exercises
1. Create a PVC and attach it to a Deployment.
2. Convert the Deployment to a StatefulSet.
3. Move a file in and out of the volume using `kubectl cp`.
