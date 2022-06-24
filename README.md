# !!! Deprecated
> There is no need to use this anymore because:
> - [AWS CLI is already in runner environment](https://stackoverflow.com/questions/59166099/github-action-aws-cli)
> - There is an [official image](https://hub.docker.com/r/amazon/aws-cli)

-----

# AWS CLI Actions

awscli using Docker image.
It is automatically updated when version of `awscli` is updated.
Insipired by [b4nst/docker-awscli](https://github.com/b4nst/docker-awscli)

## Example
 
### Print version of awscli

```yaml
- name: Echo version of aws-cli
  uses: 1inch-exchange/1inch-exchange-aws-cli@v1.0.1
  with:
    args: --version
```

### Upload files to AWS S3rc

```yaml
- name: Upload files
  uses: 1inch-exchange/1inch-exchange-aws-cli@v1.0.1
  with:
    args: s3 cp test.txt s3://bucket-name/
  env:
    AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
    AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
    AWS_DEFAULT_REGION: ap-northeast-2
```

## Sources

* https://pypi.org/pypi/awscli
* https://github.com/b4nst/docker-awscli
