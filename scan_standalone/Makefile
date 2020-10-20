CUDA_INCLUDEPATH=/pa/hal/private/installs/cuda-9.1/
NVCC_OPTS=-O3 -arch=sm_75 -Xcompiler -Wall -Xcompiler -Wextra -m64 

scan: main.cu scan.o Makefile
	nvcc -o scan main.cu scan.o $(NVCC_OPTS)

scan_ccg: main.cu scan_with_ccg.o Makefile
	nvcc -o scan main.cu scan_with_ccg.o $(NVCC_OPTS)	

scan.o: scan.cu
	nvcc -c scan.cu $(NVCC_OPTS)

scan_with_ccg.o: scan_with_ccg.cu
	nvcc -rdc=true -c scan_with_ccg.cu $(NVCC_OPTS)	

clean:
	rm -f *.o scan scan_ccg
