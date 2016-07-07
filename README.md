# WorldlyTestApp

- Add `worldly` as dependency in `mix.exs`

      defp deps do
        [{:worldly, github: "vinsol/worldly", branch: "test/country"}]
      end

- Get the worldly dependency `mix deps.get`

- Add `yamerl` and `worldly` as application dependency in `mix.exs`

      def application do
        [applications: [:logger] ++ [:yamerl, :worldly]]
      end

- Add data_path config in `config/config.exs`

      config :worldly, :data_path, Path.join(Mix.Project.deps_path, "/worldly/data")

- Start IEx `iex -S mix`
- Play with Worldy

      iex> Worldy.Country.with_name("India")
      [%Worldly.Country{alpha_2_code: "IN", alpha_3_code: "IND", common_name: "",
        has_regions: true, name: "India", numeric_code: "356",
        official_name: "Republic of India"}]

Check worldly [README](https://github.com/vinsol/worldly)
