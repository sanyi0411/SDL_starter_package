# SDL_starter_package

Basic repo to start a project with SDL, SDL_image and gtest

## How to clone

- _SDL_, _SDL_image_ and _gtest_ are added as submodules so to clone run
```
git clone --recurse-submodules https://github.com/sanyi0411/SDL_starter_package.git
```

## How to build

- `cd` into the cloned folder
- Run `cmake ..`
    - Alternatively, if you want to build the unit tests also, run `cmake .. -DBUILD_TESTS=1`
- Run `cmake --build .`