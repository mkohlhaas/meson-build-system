project('Syntax', 'c', version: '0.2.3', default_options: ['warning_level=3'])

exe = executable('Syntax', 'syntax.c', install: true)

test('basic', exe)

# Variables

var1 = 'hello'
var2 = 102

var1 = [1, 2, 3]
var2 = var1
var2 += [4]
message(var1) # var1 is still [1, 2, 3]
message(var2) # var2 is now [1, 2, 3, 4]

# Numbers

x = 1 + 2
y = 3 * 4
d = 5 % 3 # yields 2

int_255 = 0xFF
int_493 = 0o755
int_1365 = 0b10101010101

string_var = '42'
num = string_var.to_int()

int_var = 42
string_var = int_var.to_string()

# Booleans

truth = true

bool_var = false
string_var = bool_var.to_string()
int_var = bool_var.to_int()

# Strings

a_string = 'this is a string'

# String concatenation

str1 = 'abc'
str2 = 'xyz'
combined = str1 + '_' + str2 # abc_xyz

# String path building

joined = '/usr/share' / 'projectname' # => /usr/share/projectname
joined = '/usr/local' / '/etc/name' # => /etc/name

multiline_string = '''#include <foo.h>
int main (int argc, char ** argv) {
  return FOO_SUCCESS;
}'''

# String index

foo = 'abcd'
message(foo[1]) # Will print 'b'
# foo[2] = 'C'     # ERROR: Meson objects are immutable!

# String formatting with .format()

template = 'string: @0@, number: @1@, bool: @2@'
res = template.format('text', 1, true) # 'string: text, number: 1, bool: true'

# Format strings (f-strings) can be used as a non-positional alternative.

n = 10
m = 'hi'
s = f'int: @n@, string: @m@' # 'int: 10, string: hi'

n = 10
m = 5

# This is not a valid format string:
s = f'result: @n + m@'

# String methods

s = 'semicolons;as;separators'
s = s.replace('as', 'are') # 'semicolons;are;separators'

define = ' -Dsomedefine '
stripped_define = define.strip() # '-Dsomedefine'

string = 'xyxHelloxyx'.strip('xy') # 'Hello'

target = 'x86_FreeBSD'
upper = target.to_upper() # 'X86_FREEBSD'
lower = target.to_lower() # 'x86_freebsd'

version = '1'
ver_int = version.to_int()

target = 'x86_FreeBSD'
is_fbsd = target.to_lower().contains('freebsd') # true
is_x86 = target.startswith('x86') # true
is_bsd = target.to_lower().endswith('bsd') # true

target = 'x86_FreeBSD'
platform = target.substring(0, 3) # 'x86'
system = target.substring(4) # 'FreeBSD'

string = 'foobar'
oo = string.substring(-5, -3) # => 'oo'
ooba = string.substring(1, -1) # => 'ooba'

components = 'a b   c d '.split() # ['a', 'b', 'c', 'd']
components = 'a b   c d '.split(' ') # ['a', 'b', '', '', 'c', 'd', '']

output = ' '.join(['foo', 'bar']) # 'foo bar'
pathsep = ':'
path = pathsep.join(['/usr/bin', '/bin', '/usr/local/bin']) # '/usr/bin:/bin:/usr/local/bin'

path = '/usr' / 'local' / 'bin' # '/usr/local/bin'

my_sources = files('syntax.c')
my_sources += files('dummy.c')

version_array = meson.project_version().split('.') # ['0', '2', '3']
api_version = '.'.join([version_array[0], version_array[1]]) # '0.2'

api_version = '@0@.@1@'.format(version_array[0], version_array[1]) # '0.2'

name = 'Meson Docs.txt#Reference-manual'
underscored = name.underscorify() # 'Meson_Docs_txt_Reference_manual'

version = '1.2.3'
is_new = version.version_compare('>=2.0') # false; supports the following operators: >, <, >=, <=, !=, ==, =

'3.6'.version_compare('>=3.6.0') == false

# Arrays

my_array = [1, 2, 'string', version]
second_element = my_array[1]
last_element = my_array[-1]

my_array += ['foo', 3, 4, api_version]

my_array += ['something']
# This also works
my_array += 'else'

my_array = [1, 2]
if 1 in my_array
  # This condition is true
endif

if 1 not in my_array
  # This condition is false
endif

# Array Methods

len_my_array = my_array.length()
three_in_my_array = my_array.contains(3)
first_elem = my_array.get(0)
last_elem = my_array.get(-1)

# Dictionaries

my_dict = {'foo': 42, 'bar': 'baz'}
# my_dict = {'foo': 42, 'foo': 43} # duplicate keys are not allowed

forty_two = my_dict['foo']
# my_dict['does_not_exist'] # ✗

my_dict = {'foo': 42, 'bar': 43}
if 'foo' in my_dict
  # This condition is true
endif

if 'not_present' in my_dict
  # This condition is false
endif

if 'foo' not in my_dict
  # This condition is false
endif

d = {'a' + 'b': 42}
k = 'cd'
d += {k: 43}

# Function calls

# Most functions take only few positional arguments but several keyword arguments, which are specified like this:

executable('progname', sources: 'prog.c', c_args: '-DFOO=1')

# Keyword arguments can be specified dynamically. This is done by passing dictionary representing the keywords to set in the kwargs keyword. The previous example would be specified like this:

d = {'sources': 'prog.c', 'c_args': '-DFOO=1'}

executable('progname1', kwargs: d)

d = {'c_args': '-DFOO'}
# executable('progname', 'prog.c', c_args: '-DBAZ=1', kwargs: d) # Error!

# Argument flattening

executable('exe1', ['foo.c', 'bar.c', 'foobar.c'])

# Going full Lisp:
l1 = ['bar.c']
executable('exe2', [[['foo.c', l1]], ['foobar.c']])

# Method calls

# Objects can have methods, which are called with the dot operator. The exact methods it provides depends on the object.
# myobj = some_function()
# myobj.do_something('now')

# If statements

var1 = 1
var2 = 2
var3 = 3
if var1 == var2
  # Evaluates to false
  # something_broke()
elif var3 == var2
  # something_else_broke()
else
  # everything_ok()
endif

opt = get_option('libdir')
if opt != 'lib'
  # do_something()
endif

# Logical operations

a = true
b = false
c = true
d = true
e = false
f = false
g = true

if a and b
  # do something
endif

if c or d
  # do something
endif

if not e
  # do something
endif

if not (f or g)
  # do something
endif

# Foreach statements

# Foreach with an array

progs = [['prog1', ['prog1.c', 'foo.c']], ['prog2', ['prog2.c', 'bar.c']]]

foreach p : progs
  exe = executable(p[0], p[1])
  test(p[0], exe)
endforeach

# Foreach with a dictionary

components = {
  'foo': ['foo.c'],
  'bar': ['bar.c'],
  'baz': ['baz.c'],
}

# # compute a configuration based on system dependencies, custom logic
conf = configuration_data()
conf.set('USE_FOO', 1)

sources_to_compile = []
foreach name, sources : components
  if conf.get('USE_@0@'.format(name.to_upper()), 0) == 1
    sources_to_compile += sources
  endif
endforeach

# Foreach break and continue

items = ['a', 'continue', 'b', 'break', 'c']
result = []
foreach item : items
  if item == 'continue'
    continue
  elif item == 'break'
    break
  endif
  result += item
endforeach
# result is ['a', 'b']

# Ternary operator

x = true == false ? 'what?' : 77

