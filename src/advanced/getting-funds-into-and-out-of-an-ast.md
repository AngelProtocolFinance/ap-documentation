# Getting Funds Into And Out Of An AST

Now that we've covered setting up your AST, it's time to get into the important stuff. The money!

<div class="tenor-gif-embed" data-postid="14103986" data-share-method="host" data-aspect-ratio="1.87" data-width="100%"><a href="https://tenor.com/view/show-me-the-money-tom-cruise-gif-14103986">Show Me The Money Tom Cruise GIF</a>from <a href="https://tenor.com/search/show+me+the+money-gifs">Show Me The Money GIFs</a></div> <script type="text/javascript" async src="https://tenor.com/embed.js"></script>

In order to be useful, ASTs need to be able to receive funds from the outside world. We refer to these as deposits on the contracts. Deposits are open to the world by default, but can be restricted to a specific whitelisted set of contributor addresses, if so desired.

Inversely, ASTs need to send money out into the world from it's pool of tokens held on hand in their Liquid balances. This could be for things like paying a supplier for services, paying employees salaries, or many other things. Like deposits, withdraws are set to be capabile of being sent to any address, though like with deposits we've added logic to allow this to be restricted to a finite list of beneficiaries.
