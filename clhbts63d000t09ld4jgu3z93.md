---
title: "Yeoman vs Plop: Which One Should You Choose?"
seoTitle: "Yeoman vs Plop: Which One Should You Choose?"
seoDescription: "Improving developer efficiency with generators"
datePublished: Sat May 06 2023 10:11:36 GMT+0000 (Coordinated Universal Time)
cuid: clhbts63d000t09ld4jgu3z93
slug: yeoman-vs-plop-which-one-should-you-choose
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682853221594/bfd029ed-a386-46be-b873-4c4ee8ea38a8.png
tags: yeoman

---

# Introduction

As we know, it's a laborious thing to generate the codebase from zero to one. There are so many things we need to do, such as lint configuration, DevOps and Pipeline configuration, auto-upgrade dependencies, GitHub issue templates etc. So that is why we need generators to reduce our workloads. In this post, I will make a comparison between [Yeoman](https://yeoman.io/) and [Plop](https://plopjs.com/). They are all popular generator tools.

# Comparison

In this section, I will make a comparison between Yeoman and Plop with the following items:

* Ecosystem
    
* Complete documentation
    
* Create the testable generator
    

## Ecosystem

The ecosystem is the most important when we make a comparison. Yeoman has provided the [Generators repository](https://yeoman.io/generators/). Your Yeoman generator will show in the list if your generator has been published to [npmjs.org](https://www.npmjs.com/), The name should be `generator-your-unique-name`, `yeoman-generator` in the keyword property.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682843432521/c0f93362-e7b4-4f50-ab11-d3d83d7add9c.png align="center")

For Plop, it didn't provide the repository that we can search the generator from it.

## Complete documentation

Yeoman and Plop both provide complete documentation. But the documentation of Yeoman will tell you how to make unit testing. It makes with JavaScript but can help me to make it with TypeScript.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684744432549/62375be7-6e04-46aa-8cb9-641f9140d8ca.png align="center")

## Create the testable generator

Yeoman provides the following test tools to help us to create the testable generator.

* [yeoman-test](https://github.com/yeoman/yeoman-test)
    
* [yeoman-environment](https://github.com/yeoman/environment)
    
* [yeoman-assert](https://github.com/yeoman/yeoman-assert)
    

Here is an example:

```typescript
const runResult = await helpers
  .create(path.join(__dirname, "../../generators/app"))
  .withOptions({
    isTesting: true,
  } as GeneratorOptions)
  .withAnswers({
    name: name,
  } as IAnswers)

test("Expect package.json is created", () => {
  assert.file("package.json")
})

test("Expect package.json have correct name", () => {
  assert.fileContent("package.json", `"name": "${name}"`)
})
```

You can see the complete example in this repository: [https://github.com/helbing/generator-example](https://github.com/helbing/generator-example).

Otherwise, Plop doesn't provide test tools to help us to create the testable generator. But I thought you can learn to write unit tests via the test cases in its [repository](https://github.com/plopjs/plop).

# How to create Yeoman Generator

%[https://youtu.be/zTu7ZFqXGck] 

# Conclusion

I have to say this is a subjective comparison. The comparison items: ecosystem, complete documentation and writing testable code, are my concern. If they are both your concern, I highly recommend you use Yeoman.