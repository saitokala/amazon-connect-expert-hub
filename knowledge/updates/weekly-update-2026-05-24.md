```python
import datetime

# Define the current date for reporting, based on the latest data provided in the RAW DATA.
# The latest commit date is 2026-05-22. Assuming the report is generated at the end of the week, let's use 2026-05-23.
CURRENT_DATE = "2026-05-23"
REPORTING_DATE_OBJ = datetime.datetime.strptime(CURRENT_DATE, "%Y-%m-%d")
SEVEN_DAYS_AGO = REPORTING_DATE_OBJ - datetime.timedelta(days=7)

terraform_updates = []
cloudformation_updates = []
rss_updates = []
blog_updates = []
whats_new_updates = []
forum_updates = []
forum_saves = 0

# Track sources that returned no updates or whose data was not provided
no_updates_sources = []
data_missing_sources = []

# --- Task 1: Terraform Provider Scan ---
terraform_raw_data = [{"sha":"d363ed1f757952e50d2ef15098c4aff15ed3167e","node_id":"C_kwDOBZHaB9oAKGQzNjNlZDFmNzU3OTUyZTUwZDJlZjE1MDk4YzRhZmYxNWVkMzE2N2U","commit":{"author":{"name":"changelogbot","email":"changelogbot@hashicorp.com","date":"2026-05-22T21:04:47Z"},"committer":{"name":"changelogbot","email":"changelogbot@hashicorp.com","date":"2026-05-22T21:04:47Z"},"message":"Update CHANGELOG.md for #48033","tree":{"sha":"b48ce0195e15a5e4060b7564731171477d183877","url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/git/trees/b48ce0195e15a5e4060b7564731171477d183877"},"url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/git/commits/d363ed1f757952e50d2ef15098c4aff15ed3167e","comment_count":0,"verification":{"verified":false,"reason":"unsigned","signature":null,"payload":null,"verified_at":None}},"url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/d363ed1f757952e50d2ef15098c4aff15ed3167e","html_url":"https://github.com/hashicorp/terraform-provider-aws/commit/d363ed1f757952e50d2ef15098c4aff15ed3167e","comments_url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/d363ed1f75792e50d2ef15098c4aff15ed3167e/comments","author":None,"committer":None,"parents":[{"sha":"ff13f62d56a885cef07513469419964c955886fb","url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/ff13f62d56a885cef07513469419964c955886fb","html_url":"https://github.com/hashicorp/terraform-provider-aws/commit/ff13f62d56a885cef07513469419964c955886fb"}]},{"sha":"ff13f62d56a885cef07513469419964c955886fb","node_id":"C_kwDOBZHaB9oAKGZmMTNmNjJkNTZhODg1Y2VmMDc1MTM0Njk0MTk5NjRjOTU1ODg2ZmI","commit":{"author":{"name":"Graham Davison","email":"gdavison@hashicorp.com","date":"2026-05-22T21:01:33Z"},"committer":{"name":"GitHub","email":"noreply@github.com","date":"2026-05-22T21:01:33Z"},"message":"Merge pull request #48033 from hashicorp/b-secretsmanager-versions-datasource\n\ndata-source/aws_secretsmanager_secret_versions: Fixes flattening","tree":{"sha":"f117cd9568d1360b3cc0cc9b9c15ead5e5e5f205","url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/git/trees/f117cd9568d1360b3cc0cc9b9c15ead5e5e5f205"},"url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/git/commits/ff13f62d56a885cef07513469419964c955886fb","comment_count":0,"verification":{"verified":True,"reason":"valid","signature":"-----BEGIN PGP SIGNATURE-----\n\nwsFcBAABCAAQBQJqEMQtCRC1aQ7uu5UhlAAAQRIQAKERlKWCUB7GbaP4AdJuzaZe\nandSKCDhs+hOuBfMivePo8sf0r+8WaTBCe0cTSGlVT68EZhY//npCVNcuSYXT0P1\naKCOJhMBr4DWwlqQ74QQ6TmvFKvsE1XQo05tmXGlqN0cvuEmUUkOk1Rd38QRSnF/\nQGYdPAfIaHhiIGQJfkNWG+BlyOzjk5Acex+5zzbWFjerQ05t2WBdkX1944jE+ZVK\nsYnif6iFfGGhsn6Wk/w4F6U7BlPr/6RfRK69un38zVCQf0SexSJcxnKQOxq5kFdx\nqyJK69kWIACns0WwRMn/B3PceugQt8hMT4G6wIaDFipKzaHL/3dCyyjcC0zaF7C2\nZPlx9MgXHmNNFuuP7l8xXDvlRC0SXowMcIEBX8j1yPmzau3BYEeJ23BOuh3AiscN\nSqeuoNDhLwKsDgxS8/gWhRBrJ7eBlrIGeqDMOpd2WrJpbVAgkmHdEYUsO9udFkQI\nuaa+hbVGTK7Oe05j8QuD+mpF5ScuXvhxC56nkHypJEhNIYmjx4lNok91HTJ5TaML\nEjUgD3dXA62oXkBu0jlpRFBUai1VNYM4X6/vXofWSIz04XzeeavqhKTgHBoSPiHM\n1z/hVBJNMtsyowwoUjaz6vPHC1Qe6ybcxeaIYOgwp3G/IKzOqNJJhnIUJpbmZCFt\n1SOuVrmX5uPtVqe9UgTY\n=cLMx\n-----END PGP SIGNATURE-----\n","payload":"tree f117cd9568d1360b3cc0cc9b9c15ead5e5e5f205\nparent 5ee7bb711ad70fb4b2566c3b9b697c3247add9f8\nparent f06d7e68045452c6557b284fdaa9da29e52ec0b9\nauthor Graham Davison <gdavison@hashicorp.com> 1779483693 -0700\ncommitter GitHub <noreply@github.com> 1779483693 -0700\n\nMerge pull request #48033 from hashicorp/b-secretsmanager-versions-datasource\n\ndata-source/aws_secretsmanager_secret_versions: Fixes flattening","verified_at":"2026-05-22T21:01:34Z"}},"url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/ff13f62d56a885cef07513469419964c955886fb","html_url":"https://github.com/hashicorp/terraform-provider-aws/commit/ff13f62d56a885cef07513469419964c955886fb","comments_url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/ff13f62d56a885cef07513469419964c955886fb/comments","author":{"login":"gdavison","id":1148298,"node_id":"MDQ6VXNlcjExNDgyOTg=","avatar_url":"https://avatars.githubusercontent.com/u/1148298?v=4","gravatar_id":"","url":"https://api.github.com/users/gdavison","html_url":"https://github.com/gdavison","followers_url":"https://api.github.com/users/gdavison/followers","following_url":"https://api.github.com/users/gdavison/following{/other_user}","gists_url":"https://api.github.com/users/gdavison/gists{/gist_id}","starred_url":"https://api.github.com/users/gdavison/starred{/owner}{/repo}","subscriptions_url":"https://api.github.com/users/gdavison/subscriptions","organizations_url":"https://api.github.com/users/gdavison/orgs","repos_url":"https://api.github.com/users/gdavison/repos","events_url":"https://api.github.com/users/gdavison/events{/privacy}","received_events_url":"https://api.github.com/users/gdavison/received_events","type":"User","user_view_type":"public","site_admin":False},"committer":{"login":"web-flow","id":19864447,"node_id":"MDQ6VXNlcjE5ODY0NDQ3","avatar_url":"https://avatars.githubusercontent.com/u/19864447?v=4","gravatar_id":"","url":"https://api.github.com/users/web-flow","html_url":"https://github.com/web-flow","followers_url":"https://api.github.com/users/web-flow/followers","following_url":"https://api.github.com/users/web-flow/following{/other_user}","gists_url":"https://api.github.com/users/web-flow/gists{/gist_id}","starred_url":"https://api.github.com/users/web-flow/starred{/owner}{/repo}","subscriptions_url":"https://api.github.com/users/web-flow/subscriptions","organizations_url":"https://api.github.com/users/web-flow/orgs","repos_url":"https://api.github.com/users/web-flow/repos","events_url":"https://api.github.com/users/web-flow/events{/privacy}","received_events_url":"https://api.github.com/users/web-flow/received_events","type":"User","user_view_type":"public","site_admin":False},"parents":[{"sha":"5ee7bb711ad70fb4b2566c3b9b697c3247add9f8","url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/5ee7bb711ad70fb4b2566c3b9b697c3247add9f8","html_url":"https://github.com/hashicorp/terraform-provider-aws/commit/5ee7bb711ad70fb4b2566c3b9b697c3247add9f8"},{"sha":"f06d7e68045452c6557b284fdaa9da29e52ec0b9","url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/f06d7e68045452c6557b284fdaa9da29e52ec0b9","html_url":"https://github.com/hashicorp/terraform-provider-aws/commit/f06d7e68045452c6557b284fdaa9da29e52ec0b9"}]},{"sha":"f06d7e68045452c6557b284fdaa9da29e52ec0b9","node_id":"C_kwDOBZHaB9oAKGYwNmQ3ZTY4MDQ1NDUyYzY1NTdiMjg0ZmRhYTlkYTI5ZTUyZWMwYjk","commit":{"author":{"name":"Graham Davison","email":"gdavison@hashicorp.com","date":"2026-05-22T20:00:59Z"},"committer":{"name":"Graham Davison","email":"gdavison@hashicorp.com","date":"2026-05-22T20:00:59Z"},"message":"Attribute constant","tree":{"sha":"3506633f666c213c468b1236e0573799502fcb7c","url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/git/trees/3506633f666c213c468b1236e0573799502fcb7c"},"url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/git/commits/f06d7e68045452c6557b284fdaa9da29e52ec0b9","comment_count":0,"verification":{"verified":False,"reason":"unsigned","signature":None,"payload":None,"verified_at":None}},"url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/f06d7e68045452c6557b284fdaa9da29e52ec0b9","html_url":"https://github.com/hashicorp/terraform-provider-aws/commit/f06d7e68045452c6557b284fdaa9da29e52ec0b9","comments_url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/f06d7e68045452c6557b284fdaa9da29e52ec0b9/comments","author":{"login":"gdavison","id":1148298,"node_id":"MDQ6VXNlcjExNDgyOTg=","avatar_url":"https://avatars.githubusercontent.com/u/1148298?v=4","gravatar_id":"","url":"https://api.github.com/users/gdavison","html_url":"https://github.com/gdavison","followers_url":"https://api.github.com/users/gdavison/followers","following_url":"https://api.github.com/users/gdavison/following{/other_user}","gists_url":"https://api.github.com/users/gdavison/gists{/gist_id}","starred_url":"https://api.github.com/users/gdavison/starred{/owner}{/repo}","subscriptions_url":"https://api.github.com/users/gdavison/subscriptions","organizations_url":"https://api.github.com/users/gdavison/orgs","repos_url":"https://api.github.com/users/gdavison/repos","events_url":"https://api.github.com/users/gdavison/events{/privacy}","received_events_url":"https://api.github.com/users/gdavison/received_events","type":"User","user_view_type":"public","site_admin":False},"committer":{"login":"gdavison","id":1148298,"node_id":"MDQ6VXNlcjExNDgyOTg=","avatar_url":"https://avatars.githubusercontent.com/u/1148298?v=4","gravatar_id":"","url":"https://api.github.com/users/gdavison","html_url":"https://github.com/gdavison","followers_url":"https://api.github.com/users/gdavison/followers","following_url":"https://api.github.com/users/gdavison/following{/other_user}","gists_url":"https://api.github.com/users/gdavison/gists{/gist_id}","starred_url":"https://api.github.com/users/gdavison/starred{/owner}{/repo}","subscriptions_url":"https://api.github.com/users/gdavison/subscriptions","organizations_url":"https://api.github.com/users/gdavison/orgs","repos_url":"https://api.github.com/users/gdavison/repos","events_url":"https://api.github.com/users/gdavison/events{/privacy}","received_events_url":"https://api.github.com/users/gdavison/received_events","type":"User","user_view_type":"public","site_admin":False},"parents":[{"sha":"a2b2ca71c1b7a545e2949ba668a29ed8d1b5ffbb","url":"https://api.github.com/repos/hashicorp/terraform-provider-aws/commits/a2b2ca71c1b7a545e2949ba668a29ed8d1b5ffbb","html_url":"https://github.com/hashicorp/terraform-provider-aws/commit/a2b2ca71c1b7a545e2949ba668a29ed8d1b5ffbb"}]}]

for commit in terraform_raw_data:
    commit_date = datetime.datetime.strptime(commit["commit"]["author"]["date"], "%Y-%m-%dT%H:%M:%SZ")
    if SEVEN_DAYS_AGO <= commit_date <= REPORTING_DATE_OBJ:
        message = commit["commit"]["message"].lower()
        if "connect" in message or "aws_connect_" in message:
            terraform_updates.append(f"- Commit `{commit['sha'][:7]}`: {commit['commit']['message']}")

if not terraform_updates:
    no_updates_sources.append("Terraform Provider AWS (no Connect-specific updates)")

# --- Task 2: CloudFormation & AWS Samples Scan ---
cloudformation_raw_data = [{"sha":"a0f43bc6d20813052892546f445037cf84c75b54","node_id":"C_kwDOAtcQndoAKGEwZjQzYmM2ZDIwODEzMDUyODkyNTQ2ZjQ0NTAzN2NmODRjNzViNTQ","commit":{"author":{"name":"Kevin DeJong","email":"kddejong@amazon.com","date":"2025-10-13T17:30:21Z"},"committer":{"name":"GitHub","email":"noreply@github.com","date":"2025-10-13T17:30:21Z"},"message":"Merge pull request #493 from francoabregu/feature/stacksets-cdk\n\nAdded AWS CDK app to create StackSets accross multiple accounts and regions","tree":{"sha":"f9f0d4acace133e0db435cabf67b8c6824e4e234","url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/git/trees/f9f0d4acace133e0db435cabf67b8c6824e4e234"},"url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/git/commits/a0f43bc6d20813052892546f445037cf84c75b54","comment_count":0,"verification":{"verified":True,"reason":"valid","signature":"-----BEGIN PGP SIGNATURE-----\n\nwsFcBAABCAAQBQJo7TctCRC1aQ7uu5UhlAAAFukQADak+y00jjr7dzkD1oao/n6n\nS3+pDGbDe/eS+2cKGO18efHbHU8cBwSDpFz1oERK5ZR3YKwitcZSdsRfcIMgI/9/\nP42xIf0EBRTU1pRwh8m+TV90ZnCWSw5wB3RwVU1s9fU9hgkJBfWKiyjo2AnQfEFZ\nKWdQ9pmWtnJD1QzeTuPj6/Q/HASbFzyNVvs1+leDotyQ3d5WxqviVGTw0xBuM2bC\n9oQgoNHUAEUP1ySJhw8pAjdCWDo9f2FVZMiOWQzy/bjVSuWByaJxdeAZ5I6OWQYG\nyHUPKmd63UxvMxfP9Vl/BzxkWfMk5Cm33OuWMMPyqjsM+9zD/GYjexke0VZD0JPW\n8l3UXcpIKiQmYEzP7Y05IynYFaWrM8rBqmv3Ht423XYuw1gWqP9V6YJzzOk0MLaC\nwwu/vYskile3St3x3EWWsmAiMO9FyVwMKHe4+R6Rwp+A+JmeK6exYi9EOJ7Hur6E\nhwXo42yQImb+CUe+3IWBRrOpbmqash79Zz3EkRyrxbBo+TSRLjdDJNBZQ4z17QwV\nudNxFlsPH7m1CXNGWS+XnqWTkDiT4UjR4peM+4MJgpf36oNfdBF+uQfBudSjxsaf\nIqBObwfibJ9cJWtwbRwpqIsZJReaDjJhxSoBEf7+jjY093IKaeiy1K0Dv+uheJeq\nqbByG74KId0ioKw4vg9J\n=jl3E\n-----END PGP SIGNATURE-----\n","payload":"tree f9f0d4acace133e0db435cabf67b8c6824e4e234\nparent 142ce6f283d285fa370adb7f9d332d7f46dac5fc\nparent b4e8fa5fe405f5aad6e80d6522ee48d307676bb0\nauthor Kevin DeJong <kddejong@amazon.com> 1760376621 -0700\ncommitter GitHub <noreply@github.com> 1760376621 -0700\n\nMerge pull request #493 from francoabregu/feature/stacksets-cdk\n\nAdded AWS CDK app to create StackSets accross multiple accounts and regions","verified_at":"2025-10-13T17:30:21Z"}},"url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/commits/a0f43bc6d20813052892546f445037cf84c75b54","html_url":"https://github.com/aws-cloudformation/aws-cloudformation-templates/commit/a0f43bc6d20813052892546f445037cf84c75b54","comments_url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/commits/a0f43bc6d20813052892546f445037cf84c75b54/comments","author":{"login":"kddejong","id":36457093,"node_id":"MDQ6VXNlcjM2NDU3MDkz","avatar_url":"https://avatars.githubusercontent.com/u/36457093?v=4","gravatar_id":"","url":"https://api.github.com/users/kddejong","html_url":"https://github.com/kddejong","followers_url":"https://api.github.com/users/kddejong/followers","following_url":"https://api.github.com/users/kddejong/following{/other_user}","gists_url":"https://api.github.com/users/kddejong/gists{/gist_id}","starred_url":"https://api.github.com/users/kddejong/starred{/owner}{/repo}","subscriptions_url":"https://api.github.com/users/kddejong/subscriptions","organizations_url":"https://api.github.com/users/kddejong/orgs","repos_url":"https://api.github.com/users/kddejong/repos","events_url":"https://api.github.com/users/kddejong/events{/privacy}","received_events_url":"https://api.github.com/users/kddejong/received_events","type":"User","user_view_type":"public","site_admin":False},"committer":{"login":"web-flow","id":19864447,"node_id":"MDQ6VXNlcjE5ODY0NDQ3","avatar_url":"https://avatars.githubusercontent.com/u/19864447?v=4","gravatar_id":"","url":"https://api.github.com/users/web-flow","html_url":"https://github.com/web-flow","followers_url":"https://api.github.com/users/web-flow/followers","following_url":"https://api.github.com/users/web-flow/following{/other_user}","gists_url":"https://api.github.com/users/web-flow/gists{/gist_id}","starred_url":"https://api.github.com/users/web-flow/starred{/owner}{/repo}","subscriptions_url":"https://api.github.com/users/web-flow/subscriptions","organizations_url":"https://api.github.com/users/web-flow/orgs","repos_url":"https://api.github.com/users/web-flow/repos","events_url":"https://api.github.com/users/web-flow/events{/privacy}","received_events_url":"https://api.github.com/users/web-flow/received_events","type":"User","user_view_type":"public","site_admin":False},"parents":[{"sha":"142ce6f283d285fa370adb7f9d332d7f46dac5fc","url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/commits/142ce6f283d285fa370adb7f9d332d7f46dac5fc","html_url":"https://github.com/aws-cloudformation/aws-cloudformation-templates/commit/142ce6f283d285fa370adb7f9d332d7f46dac5fc"},{"sha":"b4e8fa5fe405f5aad6e80d6522ee48d307676bb0","url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/commits/b4e8fa5fe405f5aad6e80d6522ee48d307676bb0","html_url":"https://github.com/aws-cloudformation/aws-cloudformation-templates/commit/b4e8fa5fe405f5aad6e80d6522ee48d307676bb0"}]},{"sha":"142ce6f283d285fa370adb7f9d332d7f46dac5fc","node_id":"C_kwDOAtcQndoAKDE0MmNlNmYyODNkMjg1ZmEzNzBhZGI3ZjlkMzMyZDdmNDZkYWM1ZmM","commit":{"author":{"name":"Kevin DeJong","email":"kddejong@amazon.com","date":"2025-10-08T15:16:04Z"},"committer":{"name":"GitHub","email":"noreply@github.com","date":"2025-10-08T15:16:04Z"},"message":"Merge pull request #492 from fbzioui/main\n\nUpdate log-setup-management and common-resources-stackset.yaml templates","tree":{"sha":"7f120129a3cc2807da6504a2730319bd1bc0c8ff","url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/git/trees/7f120129a3cc2807da6504a2730319bd1bc0c8ff"},"url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/git/commits/142ce6f283d285fa370adb7f9d332d7f46dac5fc","comment_count":0,"verification":{"verified":True,"reason":"valid","signature":"-----BEGIN PGP SIGNATURE-----\n\nwsFcBAABCAAQBQJo5oA0CRC1aQ7uu5UhlAAA4FIQAIz96kTBjVatIwRFq+zAGs9F\n9Cgql+85l8MKez/sfNoCX7IaZSdadtFLQG53Vl5V5MSCrhiCOlRepPd63H+JCkNC\n7hMWKMjMqhG2EehByNJldOzB0OaZnJqIY3Tjaelu/EAwoXEAVaKRWkHlQQC5pwzH\n9T4xjcYD+dxydDvB0iA271plmBh/W7008oR4OfkZkKzZcYhqstqjlfcXa/IkfOOB\nggw4a52tQL5kDN0eJmvfHaiaQ0RWnvn7/J0XhMjWLhhvXIaZmDvOUMdKF9Ctlb0H\nBgrokl4hMcaF9CBa0/npBlkjirXmlUKhHX5Rgl9L7DxLdEYPHCWbHnJOQp7xFS5P\nZm8v1lMcX0d0KT+DNNbyyNPgkTtcEXil4g7ycElM0buvq2/88XXPcmnlsDZdd3DN\nBhLH6E9kweXiyYhB2iMEOotDh5QxBOlgvy1CADKRbMlZKICIBCPXEt81uLVew0NW\nWSZK6SIG9y+Err+skt5+3dgbT9YCw1xwb6YBob3lrBRenGWKsqLRhMAghcF0Q5uT\nVMdC1nCgd3UoUPzuKMaCk5P9Ql3IC5+XlIMIoOv9VEZLfkBZWoBGcDYViYAZDYEV\nUqn4l3ZwiP8seRwpaAPm3ClgB84b7OqQHN6qcKt0LCvo/Cm77+0dpeMzs0gLBwni\nBJCSQaCYDhOswRraPr9o\n=BQtq\n-----END PGP SIGNATURE-----\n","payload":"tree 7f120129a3cc2807da6504a2730319bd1bc0c8ff\nparent ff279b641bbfc0809134b332947bf2b0b16e110c\nparent 1d59468d1ead432837e707a40d2a58e4bf61aa8e\nauthor Kevin DeJong <kddejong@amazon.com> 1759936564 -0700\ncommitter GitHub <noreply@github.com> 1759936564 -0700\n\nMerge pull request #492 from fbzioui/main\n\nUpdate log-setup-management and common-resources-stackset.yaml templates ","verified_at":"2025-10-08T15:16:04Z"}},"url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/commits/142ce6f283d285fa370adb7f9d332d7f46dac5fc","html_url":"https://github.com/aws-cloudformation/aws-cloudformation-templates/commit/142ce6f283d285fa370adb7f9d332d7f46dac5fc","comments_url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/commits/142ce6f283d285fa370adb7f9d332d7f46dac5fc/comments","author":{"login":"kddejong","id":36457093,"node_id":"MDQ6VXNlcjM2NDU3MDkz","avatar_url":"https://avatars.githubusercontent.com/u/36457093?v=4","gravatar_id":"","url":"https://api.github.com/users/kddejong","html_url":"https://github.com/kddejong","followers_url":"https://api.github.com/users/kddejong/followers","following_url":"https://api.github.com/users/kddejong/following{/other_user}","gists_url":"https://api.github.com/users/kddejong/gists{/gist_id}","starred_url":"https://api.github.com/users/kddejong/starred{/owner}{/repo}","subscriptions_url":"https://api.github.com/users/kddejong/subscriptions","organizations_url":"https://api.github.com/users/kddejong/orgs","repos_url":"https://api.github.com/users/kddejong/repos","events_url":"https://api.github.com/users/kddejong/events{/privacy}","received_events_url":"https://api.github.com/users/kddejong/received_events","type":"User","user_view_type":"public","site_admin":False},"committer":{"login":"web-flow","id":19864447,"node_id":"MDQ6VXNlcjE5ODY0NDQ3","avatar_url":"https://avatars.githubusercontent.com/u/19864447?v=4","gravatar_id":"","url":"https://api.github.com/users/web-flow","html_url":"https://github.com/web-flow","followers_url":"https://api.github.com/users/web-flow/followers","following_url":"https://api.github.com/users/web-flow/following{/other_user}","gists_url":"https://api.github.com/users/web-flow/gists{/gist_id}","starred_url":"https://api.github.com/users/web-flow/starred{/owner}{/repo}","subscriptions_url":"https://api.github.com/users/web-flow/subscriptions","organizations_url":"https://api.github.com/users/web-flow/orgs","repos_url":"https://api.github.com/users/web-flow/repos","events_url":"https://api.github.com/users/web-flow/events{/privacy}","received_events_url":"https://api.github.com/users/web-flow/received_events","type":"User","user_view_type":"public","site_admin":False},"parents":[{"sha":"ff279b641bbfc0809134b332947bf2b0b16e110c","url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/commits/ff279b641bbfc0809134b332947bf2b0b16e110c","html_url":"https://github.com/aws-cloudformation/aws-cloudformation-templates/commit/ff279b641bbfc0809134b332947bf2b0b16e110c"},{"sha":"1d59468d1ead432837e707a40d2a58e4bf61aa8e","url":"https://api.github.com/repos/aws-cloudformation/aws-cloudformation-templates/commits/1d5"}]

for commit in cloudformation_raw_data:
    commit_date = datetime.datetime.strptime(commit["commit"]["author"]["date"], "%Y-%m-%dT%H:%M:%SZ")
    if SEVEN_DAYS_AGO <= commit_date <= REPORTING_DATE_OBJ:
        message = commit["commit"]["message"].lower()
        if "amazon connect" in message:
            cloudformation_updates.append(f"- Commit `{commit['sha'][:7]}`: {commit['commit']['message']}")

if not cloudformation_updates:
    no_updates_sources.append("AWS CloudFormation (no Connect-specific updates, and dates out of range)")

# No raw data for aws-samples organization
data_missing_sources.append("AWS Samples organization (no data provided)")

# --- Task 3 & 4: RSS & Community Forum Scan (Data Missing) ---
# The RAW DATA TO PROCESS section ends abruptly before the curl outputs for RSS feeds and re:Post.
# Therefore, these tasks cannot be fully performed.
data_missing_sources.append("All Official AWS Release Notes & Blog RSS Feeds (curl outputs not provided)")
data_missing_sources.append("AWS re:Post Amazon Connect Forum (curl output not provided)")

# --- Task 5: Output Generation ---
briefing_content = f"""# Amazon Connect Weekly Harvester Briefing - {CURRENT_DATE}

This is your weekly briefing on updates across the Amazon Connect ecosystem.

## 🚨 Breaking Changes & IaC Updates

**Terraform AWS Provider:**
"""
if terraform_updates:
    briefing_content += "\n".join(terraform_updates)
else:
    briefing_content += "No updates affecting `connect` or `aws_connect_*` resources were found in the `hashicorp/terraform-provider-aws` repository within the last 7 days. Recent commits focused on `aws_secretsmanager_secret_versions` data source fixes."

briefing_content += f"""

**AWS CloudFormation:**
"""
if cloudformation_updates:
    briefing_content += "\n".join(cloudformation_updates)
else:
    briefing_content += "No new or updated templates containing \"Amazon Connect\" were identified in the `aws-cloudformation/aws-cloudformation-templates` repository within the last 7 days. The most recent commits found were from October 2025 and did not relate to Amazon Connect."

briefing_content += f"""

## 🏗️ New Blueprints & Features

**Official AWS Release Notes & Blogs:**
The RSS feed content for Core Amazon Connect, Agent Workspace, Integrated CCaaS Services (Lex, Bedrock, Amazon Q), and AWS Blogs was not available for processing. Therefore, no new features, GA announcements, or deprecation notices could be extracted from these sources this week.

## 🗣️ Community Pulse & Workarounds

**AWS re:Post Amazon Connect Forum:**
The content from the AWS re:Post Amazon Connect tag was not available for processing. As a result, no insights into undocumented behaviors, bugs, or community workarounds could be gathered, and no verified solutions were saved this week.
"""

# Save the briefing file
briefing_file_path = f"knowledge/updates/{CURRENT_DATE}-weekly.md"
github_mcp_server.create_file(
    path=briefing_file_path,
    content=briefing_content,
    commit_message=f"Automated Knowledge Hub Update: {CURRENT_DATE}",
    branch="main"
)

# --- Task 6: Run Observability ---
total_updates_found = len(terraform_updates) + len(cloudformation_updates) + len(rss_updates) + len(blog_updates) + len(whats_new_updates) + len(forum_updates)
deprecations_flagged = 0 # No data to find deprecations

observability_issue_body = f"""## Sentinel Run Summary: {CURRENT_DATE}

This report summarizes the findings from the weekly Amazon Connect ecosystem harvest.

**Total Updates Found Across All Sources (from processed data):** {total_updates_found}
*   No specific Amazon Connect related updates were found in the Terraform AWS Provider.
*   No specific Amazon Connect related updates were found in AWS CloudFormation templates.

**Deprecations Flagged:** {deprecations_flagged}
*   No deprecations were identified from the data processed this week.

**Forum Thread Summaries Saved:** {forum_saves}
*   No community forum threads were saved to `knowledge/forums/` this week.

**Sources That Returned No Updates / Data Not Available:**
"""

if no_updates_sources:
    for source in no_updates_sources:
        observability_issue_body += f"*   **{source}**\n"
if data_missing_sources:
    for source in data_missing_sources:
        observability_issue_body += f"*   **{source}**\n"
if not no_updates_sources and not data_missing_sources:
    observability_issue_body += "*   All sources processed successfully and some updates were found (though none specifically for Connect in this run from provided data).\n" # This is a placeholder, as my current execution will always have missing/no updates.

github_mcp_server.create_issue(
    title=f"Sentinel Run: {CURRENT_DATE}",
    body=observability_issue_body
)
```