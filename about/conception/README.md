# Conception

We are exploring the deeper questions upon which Exercism is built: how do people learn, what drives motivation, and how do we best support people as they work towards their goals.

At the moment we have delved into the questions at a philosophical level.

**Please note that we are choosing to _not_ tackle the practical implications of these philosophical decisions at this time.**

Once we feel that we have gotten the fundamental, driving questions right, we will explore how this will play out in terms of user flows, features, wireframes, and visual design.

## Motivation

One of the core principles of Exercism is that people should do the exercises because they _want to_. Participation is voluntary, which means that we need to do our best to enhance motivation and break down barriers to success and fulfillment.

The book [How Learning Works][how-learning-works] explores three different axes along which people's motivation is strengthened or weakened.

* [**Perceived Value**](#perceived-value), explored in more depth in
  * [The Goals of Exercism][product-goals]
  * [Goals, Hopes and Dreams][user-goals]
* [**Expectancies of Success**](#expectancies-of-success), explored in more depth in
  * [Progression][progression]
* [**Environment**](#environment), explored in more depth in
  * [Emotional Journey][emotional-stages]
  * [Code Review][code-review]

## Perceived Value

Perceived value can be linked to either the activity itself, or to outcomes. It might be intrinsic or extrinsic. It might be related to the learning, the challenge, social aspects of participating in the process, or something completely different. Value is deeply personal.

We think that there are some broad themes in why people use Exercism. We've thought about what we believe Exercism can and should offer, how this aligns with people's goals, and the emotions that successful participation elicits.

In the early days of Exercism, we did not have a clear concept of what problem Exercism was solving, and what value it delivered. As a result we did a poor job of communicating why you might use Exercism, and to what purpose. We have improved our own understanding dramatically since then, but have been less than successful in communicating this to potential participants.

We have documented our thinking about [our goals][product-goals] and [their goals][user-goals], as communicating this clearly will be key to enhancing the motivation of those whose goals Exercism supports.

## Expectancies of Success

People are more likely to be motivated if they believe they can succeed. Believing that they can succeed stems from:

* having a clear plan of action
* believing that following the plan will lead to the desired outcome
* believing that they, personally, are capable of pursuing the plan to completion

Historically Exercism's language tracks have had a clear plan of action: _do each exercise in succession until you're done_. It doesn't naturally follow, however, that following this plan will make you successful, nor are tracks structured to help ensure that people are able to follow through.

As we explored the questions around success and motivation, it became clear that each exercise must feel like a step forward on a journey. Completion and progression are key.

We are proposing [a new model for progression][progression] which we believe is much more likely to provide positive expectations of success.

## Environment

In a hostile environment people need to continuously come up with reasons not to quit. In a supportive environment people are much more likely to be successful.

We believe that there are three key times in a user's journey where we need to mitigate negative emotions in order to provide an environment that is supportive.

* investing (time and effort) in a new online product
* learning to code
* receiving feedback

We've written in depth about the user's [emotional journey][emotional-stages] through these three stages of using Exercism.

Feedback and code review is one area where Exercism provides unique value. Historically, however, it is also where we have struggled the most.

In [exercism/discussions#123][gamification], [@nilbus][] evaluates code review on Exercism against the elements of gameful design:

> The code review system, viewed through a skill atom lens, is poorly designed for amplifying intrinsic value. The goals that the system communicates are weakly linked with learners' most likely motivations. Therefore, there is little motivation to overcome the challenges involved with providing good feedback and asking good questions. There are no expressed rules or guidelines to help focus reviews. Review feedback appears to be uncommon, and there are no suggestions for how to gain the most benefit from the code review process. There are plenty of intrinsic benefits in code review that could be amplified by Exercism, but these are not communicated effectively such that users will learn about or be reminded of them.

Therefore, we have invested great effort into considering how to make [code review][code-review] on Exercism supportive and integral to people's success.

[how-learning-works]: https://www.amazon.com/How-Learning-Works-Research-Based-Principles/dp/0470484101/
[product-goals]: /about/goal-of-exercism.md
[user-goals]: /about/conception/goals.md
[progression]: /about/conception/progression.md
[emotional-stages]: /about/conception/emotional-stages/README.md
[code-review]: /about/conception/code-review.md
[gamification]: https://github.com/exercism/discussions/issues/123
[@nilbus]: https://github.com/nilbus
