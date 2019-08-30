# Configure AWS Credentials

{% hint style="info" %}
If you already have a profile, you may just use it as it is and skip this step.
{% endhint %}

If you already don't have one, create an IAM user and note `aws_access_key_id` and `aws_secret_access_key` values. We will put these into `~/.aws/credentials` file. We also chose `us-east-1` as the default region.

```bash
$ emacs ~/.aws/credentials

[lambda-developer]
region = us-east-1
aws_access_key_id = AKIAQ3QMA6QD7BA7NKHW
aws_secret_access_key = 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
```

Export the profile to use

```bash
$ export AWS_DEFAULT_PROFILE=lambda-developer
```

{% hint style="info" %}
Credentials above are fake, but yours should look very similar.
{% endhint %}



