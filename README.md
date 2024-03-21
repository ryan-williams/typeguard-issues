# typeguard-issues
Repros of 2 [typeguard] issues:

## 1. `Callable`s with `Optional` args ([#typeguard#442](https://github.com/agronholm/typeguard/issues/442))

[test_callables.py](src/test_callables.py): passing a `Callable` with `Optional` args to another function, then calling it, results in a `TypeCheckError`:

```
TypeCheckError: argument "fn" (function) has too many mandatory positional arguments in its declaration; expected 0 but 1 mandatory positional argument(s) declared
```

([Github Actions example][GHA callable])

## 2. `typing_extensions.TypedDict` vs. `typeguard_ignore` wrapper ([#typeguard#443](https://github.com/agronholm/typeguard/issues/443))
[test_typeddict.py](src/test_typeddict.py): using `typing_extensions.TypedDict` and a trivial `typeguard_ignore` wrapper results in a `TypeError`:

```
TypeError: TypedDict does not support instance and class checks
```
([Github Actions example][GHA typeddict])

[typeguard]: https://github.com/agronholm/typeguard
[GHA callable]: https://github.com/ryan-williams/typeguard-issues/actions/runs/8367660052/job/22910449378#step:6:92
[GHA typeddict]: https://github.com/ryan-williams/typeguard-issues/actions/runs/8367660052/job/22910449378#step:6:121
