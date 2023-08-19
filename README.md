# Nullplatform Secrets And Variables Composite GitHub Action

You can use the GitHub Action to query Nullplatform application secrets and variables

## Change action.yml

The action.yml defines the inputs and output for your action.

Update the action.yml with your name, description, inputs and outputs for your action.

See the [documentation](https://help.github.com/en/articles/metadata-syntax-for-github-actions)

## Package for distribution

Update version in ``update-version.sh`` file changing ``VERSION_NUMBER`` and then run:

```bash
chmod 400 ./update-version.sh
```

```bash
./update-version.sh
```

## Usage

You can now consume the action by referencing the v1 branch

```yaml
uses: nullplatform/github-action-secrets-and-variables@v1
with:
  application-id: 123456
  # these are the default values
  # name: DB_CONNECTION_STRING
  # api-key: ${{ secrets.NULLPLATFORM_API_KEY }}
```
