# How it Works

Applitools easily integrates with your existing tests – no need to create new tests or learn new frameworks. With a single snippet of code, Applitools Eyes captures and analyzes an entire screen of your application.

Applitools SDKs support all major automated testing frameworks and allow you  to easily take screenshots of pages, elements, regions or iFrames and upload them along with DOM snapshots to the Applitools Eyes server. Our Visual AI then compares them with previous test executions' screenshots (aka Baselines) and reports if there is a bug or not. It's that simple!

## Baseline vs. Checkpoint images

When you first run the test, our AI engine stores those first set of screenshots as **Baseline images**. When you run the same test again (and everytime there after), the AI server compares the new set of screenshots, aka **Checkpoint images**, with the corresponding **Baseline images** and highlights differences in a pink color.

<img class="imageBoxShadow" :src="$withBase('/baselineVsCheckpoint.png')" alt="Baseline vs Checkpoint" />

<div style="text-align:center;color:gray;padding-bottom:10px;">
  The picture above is showing the Side-by-Side view of the baseline and checkpoint images
</div>

## Marking the test as "Pass" or "Fail"

When the AI compares the baseline and the checkpoint image, if it finds a legitimate difference, it will mark the test as **Unresolved**. This is because the AI doesn't know if the difference is because of a new feature or a real bug, and will wait for you to mark it as a Pass/Fail for the 1st time.

If you mark the **Unresolved** checkpoint image as <strong>"Failed"</strong>, it will only mark the current test result as Failed.

<img class="imageBoxShadow" :src="$withBase('/markItAsAFail.png')" alt="Mark the checkpoint as a fail" />

<div style="text-align:center;color:gray;padding-bottom:10px;">
  The picture above is showing how to mark the checkpoint image as Failed
</div>

::: tip Note: To automatically mark the checkpoint as a "Fail" in future test runs, you need to do the following:
  1. Annotate at least one of differences as a "<a href="https://help.applitools.com/hc/en-us/articles/360007188391-Bug-Region-Collaboration-feature-" target="_blank">bug region</a>"
  2. Select the "Fail tests" checkbox in the popup window
  3. Press the "Thumbs Up" (not "Thumbs Down") button in the checkpoint image's toolbar
  4. Press "Save" in the main toolbar
:::

If you mark the **Unresolved** checkpoint image as a "Pass", then it means that the difference is due to a new feature so we set the new checkpoint image as the **new baseline** and mark the current test as Pass. Going forward we'll compare any future tests with this new baseline.

<img class="imageBoxShadow" :src="$withBase('/markItAsPass.png')" alt="Mark the checkpoint as a Pass" />

<div style="text-align:center;color:gray;padding-bottom:10px;">
  The picture above is showing how to mark the checkpoint image as Passed
</div>

::: tip Note: Applitools AI has been trained with 100's of millions of images
It doesn't do pixel-to-pixel comparison as this can lead to a lot of false positives. It instead simulates human eyes that ignore differences that humans can't detect and highlight differences that humans can detect.

Our AI's current **accuracy rate is 99.9999%**! Which means for most applications the odds that you'll see false-positives are 1 in a million!
:::

## A powerful test results dashboard
We provide a state-of-the-art dashboard that makes it very easy for you to analyze differences, report bugs, and much more. For more information on the Applitools dashboard check out the [Applitools docs.](https://applitools.com/docs/)

<img class="imageBoxShadow" :src="$withBase('/analyzing-test-results.gif')" alt="Seeing test result summary" />

<div style="text-align:center;color:gray;padding-bottom:10px;">
  The picture above is showing the summary view
</div>

</div>