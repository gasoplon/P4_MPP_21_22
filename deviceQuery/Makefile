GCC  = g++
NVCC = nvcc

CUDA_DIR = $(CUDA_HOME)
CUDA_LIB = -L$(CUDA_DIR)/lib64
CUDA_INC = -I$(CUDA_DIR)/include
CUDA_INC_COMMON = -I$(CUDA_DIR)/samples/common/inc/

C_FLAGS = -O3
NVCC_FLAGS = -m64
LD_LIBS	= -lcudart -lm
GENCODE_FLAGS = -Wno-deprecated-gpu-targets

FILE = 

$(FILE): $(FILE).o
	 $(GCC) $(C_FLAGS) $< -o $(FILE) $(CUDA_LIB) $(LD_LIBS)

$(FILE).o: $(FILE).cu
	   $(NVCC) $(NVCC_FLAGS) $(CUDA_INC) $(CUDA_INC_COMMON) $(GENCODE_FLAGS) -o $@ -c $<

run:
	./$(FILE)

clean:
	rm -f *.o $(FILE)

