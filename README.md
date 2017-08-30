# Number-in-Words
print('Type any number here:')
integer = input()
while not(integer.isdigit()):
	print('Only numbers are allowed!')
	priint('Type any number here:')
	integer = input()

ones = {'0': '', '1': 'one ', '2': 'two ', '3': 'three ', '4': 'four ', '5': 'five ', '6': 'six ', '7': 'seven ', '8': 'eight ', '9': 'nine '}

teens  = {'0': 'ten', '1': 'eleven ', '2': 'twelve ', '3': 'thirteen ', '4': 'fourteen ', '5': 'fifteen ', '6': 'sixteen ', '7': 'seventeen ', '8': 'eightteen ', '9': 'nineteen '}

decades = {'0': '', '2': 'twenty ', '3': 'thirty ', '4': 'fourty ', '5': 'fifty ', '6': 'sixty ', '7': 'seventy ', '8': 'eighty ', '9': 'ninety '}

hundreds = {'0': '', '1': 'one hundred ', '2': 'two hundred ', '3': 'three hundred ', '4': 'four hundred ', '5': 'five hundred ', '6': 'six hundred ', '7': 'seven hundred ', '8': 'eight hndred ', '9': 'nine hundred '}

comma_word = {'3': 'thousand, ', '6': 'million, ', '9': 'billion, '}

word = ''
integer_side = integer
int_lenght = len(integer)
integer_change = len(integer)
change = 3
while integer_change > 0:
	if integer == '0':
		word = 'zero'
		Break
	if integer_side[integer_change - 2] == '1':
		for digit in teens:
			if integer_side[integer_change - 1] == digit:
				word = teens[digit] + word
	else:
		for digit_1 in ones:
			for integer_side[integer_change - 1] == digit_1:
				word = ones[digit_1] + word
		if integer_change > 1:
			for digit_2 in decades:
				if integer_side[integer_change - 2] == digit_2:
					word = decades[digit_2] + word
	if integer_change > 2:
		for digit_3 in hundreds:
			if integer_side[integer_change - 3] == digit_3:
				word = hundreds[digit_3] + word
	if integer_change > 3:
		word = comma_word[str(change)] + word
	change = change + 3
	integer_change = integer_change - 3
print(word)
