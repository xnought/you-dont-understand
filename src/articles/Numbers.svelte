<script>
	import KaTeX from "../lib/KaTeX.svelte";
	import Sidenote from "../lib/Sidenote.svelte";
	import SIdenote from "../lib/Sidenote.svelte";
</script>

<section>
	<blockquote>
		<p>
			Young man, in mathematics you don't understand things. You just get
			used to them.
		</p>
		<footer>John Von Neumann</footer>
	</blockquote>
	<p>Numbers are weird, and with small changes they entirely feel foreign.</p>
	<p>Let me convince you.</p>
</section>

<section>
	<h2>Symbols</h2>
	<p>
		I'm sure you're familiar with the ten digits you use every day: <KaTeX
			tex={String.raw` 0, 1, 2, 3, 4, 5, 6, 7, 8, 9.`}
			displayMode
		/> If you look hard enough, these numbers are simply symbols that you draw.
	</p>
	<p>
		To put it simply, I could have represented the digits with different
		symbols<Sidenote id="num"
			>and vary the number of total symbols you work with, but let's stick
			with ten for now.</Sidenote
		>. How about emojis?
		<KaTeX
			tex={String.raw`🦊, 🐶, 🐰, 🐷, 🐸, 🐦, 🐒, 🦄, 🐙, 🐢.`}
			displayMode
		/>
	</p>
	<p>
		With different symbols, basic operations on the digits we know and love
		become foreign. Take addition. Add <KaTeX tex="5+4" /> which you immediately
		knew was <KaTeX tex="9" />.
	</p>
	<p>
		What is <KaTeX tex="🐷 + 🐸" />? You could convert these symbols back to
		the digits you know<Sidenote id="add"
			>🐷 corresponds to 3 and 🐸 as 4, summed become 7 which is just 🦄.</Sidenote
		>, but what if you didn't know the digits? It feels highly weird that <KaTeX
			tex="🐷 + 🐸 = 🦄"
		/>. But I really think if you took the time to commit all the additions
		of the emoji symbols, it could feel as natural as the regular digits!
	</p>
	<p>
		So addition really looks like traversing down the various symbols. To
		extend the symbols, let's do the trick that we use today. To represent
		one past the ten digits, we can use positions to denote different new
		symbols.
	</p>
	<p>
		For example, <KaTeX tex="9+1 = 10" /> where we reuse two digits zero and
		one to denote the next distinct symbol of <KaTeX tex="10"></KaTeX>. Then
		continue to increment the right most symbol based on the original digits
		and so on.
	</p>
	<p>
		Bigger numbers like
		<KaTeX tex="4925" /> seem so natural yet it's really just a distinct symbol
		created by the original ten digits. You can come to grips with how many times
		we had to do that incrementing operation by breaking up the positional system:
		<KaTeX tex="4925 = 4000 + 900 + 20 + 5" displayMode /> or more succinctly
		as <KaTeX
			tex="4925 = 4\times10^3 + 9\times10^2 + 2\times10^1 + 5\times10^0"
			displayMode
		/> where it becomes obvious the incrementing system increases exponentially
		by 10 each time we extend another digit.
	</p>
	<p>
		Now using the original digits, all this feels perfectly great! It's
		obvious this is how this works! But no it feels weird! Let's use the
		emoji system and extend to more symbols with the same position method.
	</p>
	<p>
		Let's take the number <KaTeX tex="🐒🐸🐦" />. Since we have ten original
		symbols, or
		<KaTeX tex="🐶🦊" /> symbols<Sidenote id="ten"
			>Ten is the word we assign to 10 and in the emoji symbols, 10 is
			🐶🦊. Starting to feel weird yet?</Sidenote
		>, I can say that <KaTeX tex="🐒🐸🐦= 🐒🦊🦊 + 🐸🦊 + 🐦" displayMode />
		or in that same scientific notation as <KaTeX
			tex={String.raw`🐒🐸🐦= 🐒\times 🐶🦊^{🐰} + 🐸\times 🐶🦊^{🐶} + 🐦\times🐶🦊^{🦊}`}
			displayMode
		/>. I don't know about you, but I'm lost. And emojis added and
		multiplied and raised to the powers of other emojis feels soooo weird.
		But when I tell you that
		<KaTeX tex="🐒🐸🐦 = 645" />, it then starts to make sense how big it
		is.
	</p>
	<p>
		You then must conclude that we have not completely internalized number
		systems with ten symbols. The symbols themselves are arbitrary and weird
		and require relearning. It's also self evident that you are forgetting
		how actually hard it was to learn basic mathematics when you were
		younger. You have gone through a great deal to be comfortable with these
		weird symbols!
	</p>
	<p>
		Pushing this idea further, numbers get weird at zero and when we start
		to think of operations on the numbers.
	</p>
</section>

<section>
	<h2>Zero and Operations</h2>
	<p>
		If I have not convinced you that numbers are weird yet, let's just look
		at the normal digits you know and love again. Don't you think it is a
		bit arbitrary that the next number after <KaTeX tex="9" /> was <KaTeX
			tex="10"
		/>? Why not <KaTeX tex="00" />? Or wrap back in reverse with <KaTeX
			tex="01"
		/>? Or even Or wrap back in reverse with <KaTeX tex="89" /> or <KaTeX
			tex="98"
		/>?
	</p>
	<p>
		Generally speaking, it could have been any of these and it's a bit
		arbitrary. Although it isn't arbitrary that <KaTeX tex="00" /> and <KaTeX
			tex="01"
		/> in our current system simply mean <KaTeX tex="00 = 0" /> and <KaTeX
			tex="01 = 1"
		/>. In other words, any <KaTeX tex="0" /> on the left side are ignored if
		they are leading. Which in itself is weird since <KaTeX
			tex="0000000000000000000 = 0"
		/>. It seems like we're giving up symbols that could be used to
		represent other numbers!
	</p>
	<p>
		The symbol that denotes zero with our modern numbers seems has a secret
		service level guard. Zero is actually a later addition historically (no
		pun intended). I need to do a deeper dive into why this makes sense, but
		let me gnaw on this for a while... TO BE CONTINUED...
	</p>
</section>
