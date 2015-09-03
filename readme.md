# Diceware Password Generator #

Roll virtual dice to determine a passphrase from a list.
Invoke the generator using `diceware-pwgen -l 8`, where 8 can be replaced by any number.
Another option is the -r flag. It shows the dice rolls.
# How is it random? #

The script uses /dev/random. This is a high quality random number generator. It collects
entropy from random noise, unless the implementation specifies otherwise.

# Is it secure? #

The passwords generated are from 7776 short words. This means that for N words, there
are 7776^N combinations. If you have 8 words in your passphrase, you have

	`7776^8 = 13367494538843734067838845976576`

This is larger than having a password containing all writable characters (126 -
31)
of length 15.

	`(126 - 31)^15 = 463291230159753366058349609375 < 7776^8`

This means that an easy-to-remember passphrase is more secure than a random permutation
of writables.

The list of words can be found at http://world.std.com/~reinhold/diceware.wordlist.asc
