---
title: Writing a commit
position: 1
---

# Writing a commit

Our approach to commit authorship Stephen Ball's [_Deliberate Git_](http://www.rakeroutes.com/blog/deliberate-git/) philsoophy. You can [watch a video of his presentation](https://vimeo.com/72762735) of this philosophy from Steel City Ruby 2013.

> “Your code can only say what it does right now. You can’t look at a method and see its history: the alternative approaches that have been considered, the algorithms that have already been outgrown, the simpler code that has been replaced, or the complicated code that’s been refactored.Not capturing this knowledge is a huge loss. In Deliberate Git I'll share how to use Git to write detailed commits that craft a cohesive story about the code without giving up a good programming flow.”
>
> Stephen Ball @ Steel City Ruby 2013

## Commit criteria

Good commits answer the following questions, as applicable.

- Does the commit title state what this commit will do when merged?
- Does the commit body explain why the change was required?
- Is it clear why this approach was taken over others?
- Was there research conducted that would be beneficial for another developer to know?
- If you used a 3rd-party site like StackOverflow or a developer’s blog post, is that resource referenced in the commit message?
- Are there conditions in which this approach might no longer be appropriate?
- Would another developer understand full scope of the change and how to leverage or extend it?

## Commit formatting

- Commit titles should be written in the active tense.  
  `Add instructions for writing a commit`  
  not  
  `Added instructions for writing a commit`
- Titles must be no longer than 72 characters
- You can use simple markdown in your commit body, but understand that in some contexts it will be displayed as plain text
- You cannot use header markdown (`#` tags) because they will be treated as code comments and the text that follows will be lost

## Examples

Below are commits that follow the Deliberate Git best practices around _what_ and _why_ they were created. They have been replicated here because some are from private repositories which viewers of this file might not have access to.

The format is:

> **[Commit title linking to commit in `master` branch]()**

> Commit message
>
> …
>
> …

> Commit author & date

### Austin Convention Center Website

> **[Work around IE bug impacting inline SVG height](47d7aa7506e0ff6d55269062012725e0af35482b)**

> By default, IE 10 and 11 render the interactive floor plan SVGs as only ~150px tall, regardless of their width. Additional CSS declarations don't seem to have any effect, so I resorted to setting the height manually, via JS, based on the SVG's viewBox aspect ratio.
>
> Note that the manual height doesn't update when the window is resized, but I don't think that's worth the trouble.

> [Jacob Paul](https://github.com/jcbpl) committed on Jan 2

### CitySpace

> **[Improve flexbox implementation](https://github.com/cityofaustin/cityspace/commit/c36e916e798593a255ae7a077ee2c90cf12bdb82)**

> `justify-content: space-between` makes the last item in a row float to the right when there are fewer items than columns. The`batch` tag in twig allows us to insert missing elements into arrays of a given size. While adding ‘blank’ items could be considered polluting the DOM for the sake of styling, I don’t think it’s terribly offensive.
>
> Had the block implementation been coded to account for the necessary margins between elements differently, we wouldn’t need to insert a spacer element, but it’s important to note that flex box is not a grid system in itself, and this is being used outside of any other grid system.
>
> To change from 3 to 2 or 4 columns across, update lines 57 and 58: `cityspace-flexbox-thirds` >> …`-halves` or …`-fourths` and `items|batch(3,` >> `items|batch(2` or `items|batch(4`.
>
> This update also allows for vertical centering of items in tiles.
>
> Tested back to IE10, where blocks line up in a single column as a fallback.
>
> Sources:
> https://stackoverflow.com/questions/18744164/flex-box-align-last-row-to-grid
> https://twig.sensiolabs.org/doc/2.x/filters/batch.html

> [Sarah Rudder](https://github.com/sknep) committed on May 30