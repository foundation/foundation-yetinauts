# Building Blocks Proposal

## Problems
The Yetinauts have identified the following problems with the current state of Building Blocks:

* There is not a well defined, streamlined submission process in place for the community to share building blocks with each other.
* Individual building blocks are no longer tied in with the docs like they were in Foundation 5.
* There are no building blocks for Foundation for Apps or Emails.
* There is no filtering of blocks by version 5/6.
* When resizing the window starting from smallest to largest, the left sidebar goes away which causes block's preview frame to jump breakpoints. They go in this order: `small -> medium -> small -> medium -> large`. This looks weird when trying to see how a building block looks at different breakpoints.
* There are no copy buttons for source code, and double clicking in the source code does not select all. This forces the user to start selecting at the top of the code and scroll all the way to the bottom which can be tedious/annonying with large blocks of code.


## Proposal for the future of Building Blocks
### Public Repo
The Yetinauts propose to move the Building Blocks to a public repo on GitHub (github.com/zurb/building-blocks)

#### Submissions
* Building blocks are submitted via PR, or by opening an issue on the repo with a link to a CodePen of the submission.
* Submissions are voted on by the Yetinauts with a thumbs up/down reaction on GitHub
* After X number of Yetinauts have voted, the building block is included or abandoned based on majority vote.
* ZURB has final say in what makes the cut.

#### Repo structure

```sh
├── building-blocks
│   ├── apps
│   │   └── rad-block-for-apps
│   │       └── blockfile.md
│   │       └── screenshot.png
│   ├── emails
│   │   └── cool-email-block
│   │       └── blockfile.md
│   │       └── screenshot.png
│   └── sites
│       ├── awesome-block
│       │   └── blockfile.md
│   	│   └── screenshot.png
│       └── neato-thing-for-sites
│           └── blockfile.md
│           └── screenshot.png
├── gulpfile.js
└── package.json
```

* Each framework (Sites, Apps, Emails) has its own directory
* Each building block is in a subdirectory of its framework 
* Each building block directory contains:
	* `blockfile.md`
	* `screenshot.png`
* Blockfile contains (see `building-blocks-blockfile-example.md`):
	* Building block title
	* Description
	* Author's GitHub username
	* Framework used
	* Version of framework used to create the original building block
	* List of framework components used in building block (used for linking building blocks in the docs for a component)
	* Tags (higher level than the components used, e.g. navigation, video, social media, etc.)

#### Build System
* The build system will parse the code blocks and information from `blockfile.md` and create a static html page for each block.
* The building blocks repo will integrate with each framework's build system to add links with screenshots of the building blocks individual building blocks in the corresponding component's page in the framework's docs.

### Building Blocks Public Site Improvements
* Copy button for source code
* Double clicking source code block selects all text in the block
* Button to launch the building block in a new Pen using the CodePen API
* Clear directions on how to contribute to building blocks or provide feedback on existing ones
* Allow users to favorite building blocks using the same account they use for the forum
* Ability to order blocks by popularity
