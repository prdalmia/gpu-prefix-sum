CUDA_INCLUDEPATH=/pa/hal/private/installs/cuda-9.1/
NVCC_OPTS=-O3 -arch=sm_70 -Xcompiler -Wall -Xcompiler -Wextra -m64 -dlcm=ca

scan: main.cu scan.o Makefile
	nvcc -o scan main.cu scan.o $(NVCC_OPTS)

scan.o: scan.cu
	nvcc -rdc=true -c scan.cu $(NVCC_OPTS)

clean:
	rm -f *.o scan
