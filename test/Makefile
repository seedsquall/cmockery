CMOCKERY_HOME=/data/zhangxi/workspace/openproject/cmockery
INC=${CMOCKERY_HOME}/src/google
LIB_PATH=/data/zhangxi/soft_install/cmockery/lib

FLAGS=-g -I${INC} -L${LIB_PATH} -Wl,-rpath=${LIB_PATH} -lcmockery -DUNIT_TESTING

APPS=run_tests assert_module_test assert_macro_test

#all : run_tests assert_module_test assert_macro_test
all : ${APPS}

%.o: %.c
	gcc $(FLAGS) -c $<

run_tests : run_tests.o
	gcc ${FLAGS} -o $@ $^

assert_module_test : assert_module_test.o assert_module.o
	gcc ${FLAGS} -o $@ $^

assert_macro_test : assert_macro.o assert_macro_test.o
	gcc ${FLAGS} -o $@ $^

clean : 
	rm ./*.o ${APPS}

