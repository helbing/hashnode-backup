---
title: "Why do you choose Renovate instead of Dependabot"
seoTitle: "Why do you choose Renovate instead of Dependabot"
seoDescription: "A better Automated dependency updates tool"
datePublished: Thu May 04 2023 10:06:44 GMT+0000 (Coordinated Universal Time)
cuid: clh8yq6uh000709mb5dh4fj15
slug: why-do-you-choose-renovate-instead-of-dependabot
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1683194719290/be00f492-11c6-40ed-8203-2879ec9a5c23.png
tags: dependency-management, renovate

---

[Renovate](https://www.mend.io/renovate/) and [Depandabot](https://github.com/dependabot) are both automated dependency update tools. They can help us to maintain projects and keep projects healthy.

## Comparison

## Supported package managers

Although Renovate and Depandabot supported many package managers, based on my experience, Renovate is more comprehensive than Dependabot, for example, until 2023-05-01, Dependabot still doesn't support `pnpm`, it's in `WIP` status, you can know furthermore in this [issue](https://github.com/dependabot/dependabot-core/issues/1736) and [PR](https://github.com/dependabot/dependabot-core/pull/7081).

## Group updates

Renovate support group updates, which means that it offers more flexible control package upgrades. This is a very important feature, for example, when I developing a CDK Construct, `aws-cdk-lib` package and `@aws-cdk` prefix for the packages needs to be the same version, which means they also need to upgrade to the same version. If you don't do that, it maybe will not pass your CI pipeline. At Renovate, you can configure it with the following group rules.

```json
{
  "packageRules": [
    {
      "groupName": "AWS CDK",
      "groupSlug": "awscdk",
      "matchPackageNames": [
        "aws-cdk-lib"
      ],
      "matchPackagePrefixes": [
        "@aws-cdk/"
      ]
    }
  ]
}
```

You can know Renovate furthermore with its [documentation](https://docs.renovatebot.com/). On the other hand, until 2023-05-01, Denpdabot still doesn't support group updates. You can know more about the following issues.

* [Support grouping for "must-be-updated-together" dependencies](https://github.com/dependabot/dependabot-core/issues/1296)
    
* [Add grouped updates](https://github.com/dependabot/dependabot-core/issues/1190)
    

# Conclusion

The comparison items above are the situation I faced during the development process. Renovate can solve them very well, but Dependabot can't. That's why I strongly recommended you use Renovate instead of Dependabot. I believe that Dependabot will solve them in the future, but that's the future thing, I have to use these features right now.