########################################################################
#
# SPL, the Shakespeare Programming Language
#
# Copyright (C) 2001 Karl Hasselström and Jon Åslund
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or (at
# your option) any later version.
#
# This program is distributed in the hope that it will be useful, but
# WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA 02111-1307,
# USA.
#
########################################################################

SPLPATH = ../spl

# compiler commands 
CC      = gcc
SPL2C = $(SPLPATH)/bin/spl2c

# compiler flags
CCFLAGS      = -O2 -Wall
INCLUDEFLAGS = -I$(SPLPATH)/include
LDFLAGS      = -L$(SPLPATH)/lib -lm -lspl

.PHONY: all
all: reverse hello primes

reverse: reverse.o 
	$(CC) $(CCFLAGS) $^ $(LDFLAGS) -o $@

reverse.c: reverse.spl
	$(SPL2C) < $< > $@

reverse.o: reverse.c
	$(CC) $(CCFLAGS) $(INCLUDEFLAGS) -c $<

hello: hello.o 
	$(CC) $(CCFLAGS) $^ $(LDFLAGS) -o $@

hello.c: hello.spl
	$(SPL2C) < $< > $@

hello.o: hello.c
	$(CC) $(CCFLAGS) $(INCLUDEFLAGS) -c $<

primes: primes.o 
	$(CC) $(CCFLAGS) $^ $(LDFLAGS) -o $@

primes.c: primes.spl
	$(SPL2C) < $< > $@

primes.o: primes.c
	$(CC) $(CCFLAGS) $(INCLUDEFLAGS) -c $<

# clean-up funtion
.PHONY: clean
clean:
	rm -f *~ *.c *.o core primes hello reverse
