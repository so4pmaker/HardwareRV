# LTL3BA - Version 1.1.2 - February 2015

# Written by Denis Oddoux, LIAFA, France                                 
# Copyright (c) 2001  Denis Oddoux                                       
# Modified by Paul Gastin, LSV, France                                   
# Copyright (c) 2007  Paul Gastin                                        
# Modified by Tomas Babiak, FI MU, Brno, Czech Republic                  
# Copyright (c) 2012  Tomas Babiak                                       
#                                                                        
# This program is free software; you can redistribute it and/or modify   
# it under the terms of the GNU General Public License as published by   
# the Free Software Foundation; either version 2 of the License, or      
# (at your option) any later version.                                    
#                                                                        
# This program is distributed in the hope that it will be useful,        
# but WITHOUT ANY WARRANTY; without even the implied warranty of         
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the          
# GNU General Public License for more details.                           
#                                                                        
# You should have received a copy of the GNU General Public License      
# along with this program; if not, write to the Free Software            
# Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA 02111-1307 USA
#                                                                        
# Based on the translation algorithm by Gastin and Oddoux,               
# presented at the 13th International Conference on Computer Aided       
# Verification, CAV 2001, Paris, France.                                 
# Proceedings - LNCS 2102, pp. 53-65                                     
#                                                                        
# Modifications based on paper by                                        
# T. Babiak, M. Kretinsky, V. Rehak, and J. Strejcek,                    
# LTL to Buchi Automata Translation: Fast and More Deterministic         
# presented at the 18th International Conference on Tools and            
# Algorithms for the Construction and Analysis of Systems (TACAS 2012)   

# Set PATH to "bdd.h" BuDDy file.
BUDDY_INCLUDE=/usr/local/include/
# Set PATH to "libbdd.a" BuDDy file.
BUDDY_LIB=/usr/local/lib/

# to obtain BuDDy run:
# $ cd some_directory
# $ wget https://downloads.sourceforge.net/project/buddy/buddy/BuDDy%202.4/buddy-2.4.tar.gz
# $ tar xzf buddy-2.4.tar.gz
# $ cd buddy-2.4
# $ ./configure
# $ make
# then set  
# BUDDY_INCLUDE=some_directory/buddy-2.4/src/
# BUDDY_LIB=some_directory/buddy-2.4/src/.libs/
# and add BUDDY_LIB path into the library path (LD_LIBRARY_PATH)
# or run 
# $ make install 
# and use the default values of BUDDY_INCLUDE and BUDDY_LIB.

CC=g++
CXX=g++
CPPFLAGS= -O3 -DNXT -I$(BUDDY_INCLUDE)

LTL3BA=	parse.o lex.o main.o trans.o buchi.o cset.o set.o \
	mem.o rewrt.o cache.o alternating.o generalized.o optim.o

ltl3ba:	$(LTL3BA)
	$(CXX) $(CPPFLAGS) -o ltl3ba $(LTL3BA) -L$(BUDDY_LIB) -lbdd

$(LTL3BA): ltl3ba.h

clean:
	rm -f ltl3ba *.o core
