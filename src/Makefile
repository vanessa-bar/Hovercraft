CC       =  gcc
CFLAGS   = -Wall -O2 -g
LIB      = -lmingw32 -lSDLmain -lSDL -lopengl32 -lglu32 -lm  
INCLUDES = 

OBJ      = main.o
RM       = rm -f
BIN      = main
DIRNAME  = $(shell basename $$PWD)
BACKUP   = $(shell date +`basename $$PWD`-%m.%d.%H.%M.tgz)
STDNAME  = $(DIRNAME).tgz

all : $(BIN)

$(BIN) : $(OBJ)
	$(CC) $(CFLAGS) $(OBJ) $(LIB) $(INCLUDES)  -o $(BIN)
	@echo "--------------------------------------------------------------"
	@echo "                 to execute type: ./$(BIN) &"
	@echo "--------------------------------------------------------------"

%.o : %.c
	@echo "compile minimal"
	gcc $(CFLAGS) -c $<
	@echo "done..."

clean :	
	@echo "**************************"
	@echo "CLEAN"
	@echo "**************************"
	$(RM) *~ $(OBJ) $(BIN) 

tar : clean 
	@echo "**************************"
	@echo "TAR"
	@echo "**************************"
	cd .. && tar cvfz $(BACKUP) $(DIRNAME)
