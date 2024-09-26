# my_livebooks

public practices on Livebook

## Run

```
cd <your_livebook_directory>
ELIXIR_ERL_OPTIONS="-epmd_module Elixir.Livebook.EPMD" LIVEBOOK_HOME="<this directory>" iex -S mix phx.server
```


## メモ

手元で作成したmoduleの組み込み

```
load_local_module = fn name ->
  file_path = Path.join([System.get_env("LB_HOME"), "modules", name])
  Code.eval_file(file_path)
end

load = fn ->
  load_local_module.("my_data_frame.ex")
end

load.()
```
