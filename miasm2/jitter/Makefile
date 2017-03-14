.PHONY : clean

LDFLAGS += -shared
CPPFLAGS += -fPIC

all: vm_mngr.so Jittcc.so arch/Jit_x86 arch/Jit_arm

Jittcc.so: Jittcc.c
	$(CC) -I /usr/include/python2.7 $(CFLAGS) $^ -o $@ $(LDFLAGS) -ltcc

vm_mngr.so: vm_mngr.c vm_mngr_py.c
	$(CC) -I /usr/include/python2.7 $(CFLAGS) $^ -o $@ $(LDFLAGS)

%.so: %.c
	$(CC) -I /usr/include/python2.7 $(CFLAGS) $^ -o $@ $(LDFLAGS)

clean:
	$(RM) $(all)
