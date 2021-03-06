## Module Types

#### `Cube`

``` purescript
data Cube
  = Cyan
  | Brown
  | Red
  | Orange
  | Yellow
```

##### Instances
``` purescript
instance showCube :: Show Cube
instance eqCube :: Eq Cube
instance ordCube :: Ord Cube
instance boundedCube :: Bounded Cube
instance enumCube :: Enum Cube
```

#### `Stack`

``` purescript
type Stack = List Cube
```

#### `Wall`

``` purescript
type Wall = List Stack
```

#### `Transformer`

``` purescript
type Transformer = Wall -> Wall
```

#### `TransformerId`

``` purescript
type TransformerId = String
```

#### `TransformerRecord`

``` purescript
type TransformerRecord = { name :: String, function :: Transformer }
```

#### `LevelId`

``` purescript
type LevelId = String
```

#### `Difficulty`

``` purescript
data Difficulty
  = Easy
  | Medium
  | Hard
```

##### Instances
``` purescript
instance showDifficulty :: Show Difficulty
```

#### `Level`

``` purescript
type Level = { name :: String, help :: Maybe String, difficulty :: Difficulty, initial :: Wall, target :: Wall }
```

#### `Chapter`

``` purescript
type Chapter = { name :: String, transformers :: StrMap TransformerRecord, levels :: StrMap Level }
```

#### `GameState`

``` purescript
type GameState = { currentLevel :: LevelId, levelState :: StrMap (List TransformerId) }
```


