CC = gcc
CFLAGS = -Wall -Wextra -std=c11
TARGET = app

all: $(TARGET)

#сборка программы
$(TARGET): main.o filelib.o
	$(CC) $(CFLAGS) -o $(TARGET) main.o filelib.o

# Компиляция main.c
main.o: main.c filelib.h
	$(CC) $(CFLAGS) -c main.c

# Компиляция filelib.c
filelib.o: filelib.c filelib.h
	$(CC) $(CFLAGS) -c filelib.c

# Запуск
run: $(TARGET)
	./$(TARGET)

# Запуск с выводом в out.txt
run-out: $(TARGET)
	./$(TARGET) > out.txt

# Запуск с ошибками в err.txt
run-err: $(TARGET)
	./$(TARGET) 2> err.txt

# Запуск с разделением потоков
run-split: $(TARGET)
	./$(TARGET) 1> out.txt 2> err.txt

# Запуск с объединением обоих потоков в all.txt
run-all: $(TARGET)
	./$(TARGET) > all.txt 2>&1

# Очистка
clean:
	rm -f *.o $(TARGET) log.txt out.txt err.txt all.txt myfile.txt output.txt error.txt
	
# Файлы для сборки
.PHONY: all run clean