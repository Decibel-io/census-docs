---
description: Use Census directly with dbt through the native dbt integration.
---

# dbt Models

Census supports connecting to an existing dbt project hosted in GitHub or GitLab, which allows you to select models you want to make available to sync into all your business tools. This means you can keep all your source code & transforms in a single repository.

Census compiles your models on the fly whenever a sync is scheduled so your data and your models are always up to date. It also means that Census can confirm that your pull requests for dbt model changes won't accidentally drop or rename a model that is currently in use. Census is designed to work hand-in-hand with dbt Cloud or any other dbt runner.

## Setting it up

Here are the instructions for connecting a dbt project:

1. **Connect to your repository** in GitHub or GitLab. If you’d prefer to use a different service, please let us know!
2. **Select the branch** you’d like Census to use. Census will refresh the project on a regular basis and detect any changes to your models. You can force a refresh at any point from the models' page.
3. **Specify the database and schema parameters** used when compiling models. These values should be the same values you use in the `profiles.yml` file for your production dbt runs. You may need to ensure that your Census data warehouse connection has read access to intermediate tables produced by your dbt run.
4. **Customize optional parameters**:
   1. _The Census model selector._ Any model exposed to Census becomes available as a source for syncing your data to external tools. By default, Census looks for models with the `census` tag but you can customize the filter. Example selectors:
      * All models with a tag: `tag:census`
      * All models in a directory: `path/to/models`
      * All models: `*`
      * For more information on selector syntax, see [dbt’s Model Selector Syntax](https://docs.getdbt.com/reference/model-selection-syntax/).
   2. _Target Profile Name._ Provide Census with your production profile's name if this value is used as a variable in a custom `generate_schema_name` macro or other location. Otherwise, leave this value as `default`.
   3. _Environment Variables_. Use the Environment Variable editor to specify the values that Census should use when compiling your dbt models.

Once you’ve configured your project repository, Census will analyze your project and display the models you’ve made available. You’re now ready to start using these models as part of Census syncs!

### [`require-dbt-version`](https://docs.getdbt.com/reference/project-configs/require-dbt-version) in `dbt_project.yml`

Census will try to match a dbt version based on the `require-dbt-version` field, if specified, in your project's `dbt_project.yml`.

* If this field is not specified, a default version of `1.4.1` will be used.
* If Census does not support a version of dbt specified by the `require-dbt-version` field, the project will not compile sucessfully.
* If Census supports multiple dbt versions that match the requirements, the latest version supported by Census will be used.

Our dbt integration currently supports version `1.0.4`, `1.2.1`, `1.3.1`, `1.4.1`, and `1.5.0`. We also post version support in our [changelog](https://whatsnew.getcensus.com/).

### Unsupported features

Our dbt integration is designed to pair nicely with your existing dbt runner, whether dbt Cloud or self-hosted. We do this by using the `dbt compile` command rather than the typical `dbt run` and then make use of the compiled output only.

As a result, there's several dbt features that Census does not make use of. These include:

* Materialization directives. Census doesn’t currently materialize your tables back to your data warehouse. Census will however use materialized tables by your dbt runner to speed up the execution
* Pre and post hooks
* Non-public packages

## dbt Model descriptions

The Census dbt Models integration re-leverages the investment you've made in your dbt project, including in documentation. Without visiting your dbt docs site, discover whether your available dbt models have the data you need for reverse ETL syncs.

Within Census, your dbt models will display your model's `description` parameter found in any `schema.yml` file to display context about the dataset.&#x20;

<figure><img src="../../../.gitbook/assets/screely-1683048647353.png" alt="Screenshot of a dbt model shown in Census. The &#x22;Description&#x22; is taken directly from the docs string you specify about your dbt model in any schema.yml file."><figcaption><p>The "Description" is taken directly from the docs string you specify about your dbt model in any schema.yml file.</p></figcaption></figure>

## dbt Continuous Integration (CI) Checks

For dbt models used in Census syncs, Census can check whether you are going to drop, rename, or move a model that will end up breaking an active sync in your account. When a Pull Request (or commit to a Pull Request) is created, dbt CI Checks will help ensure that your dbt development never unexpectedly breaks downstream Census syncs.

### Installing Checks

To enable these CI checks, navigate to your dbt integration in Census and click "Enable CI/CD Tests in GitHub".

![You can find dbt Checks in a new section of your dbt integration, under "Automatic tests in dbt".](<../../../.gitbook/assets/Screen Shot 2022-08-10 at 3.43.09 PM.png>)

Once you enable CI checks, Census will automatically run a sample check on a PR. You can then view the PR to see the results of the check.

![](<../../../.gitbook/assets/Screen Shot 2022-08-10 at 4.38.56 PM.png>)

If any tests do not pass, you can click "Details" to view more information about the results. You'll see a report of any broken models and their dependent syncs, with links to investigate these syncs further in Census.

![A detailed view of the test failures.](<../../../.gitbook/assets/Screen Shot 2022-08-10 at 4.39.19 PM.png>)

## Coordinating with dbt Cloud

If you're using dbt Cloud to run your dbt project, our integration goes even further. You can configure Census to automatically run syncs whenever your models have been rebuilt. See our documentation on [connecting and configuring dbt Cloud](../../core-concept/triggering-syncs.md#dbt-cloud-integration).

## Required data warehouse permissions

Census doesn't necessarily require the same permissions your dbt project needs because Census only runs the models you've exposed to Census during set up. Census only requires read access to your selected models and any of their materialized dependencies. That means you can use dbt's materialize configuration flag to create permissions boundaries. Once materialized dependencies are generated by dbt runner, Census will reference the materialized results when accessing your models.

