TODO: Migrating wasp-os for PineTime to NimBLE Bluetooth Stack and MCU Manager Firmware Update

.. code-block:: sh

   clear; make -j `nproc` BOARD=pinetime V=1 micropython

   zsh: command not found: nproc
   #### TODO make -C micropython/mpy-cross
   rm -f micropython/ports/nrf/build-pinetime-s132/frozen_content.c
   make -C micropython/ports/nrf \
         BOARD=pinetime SD=s132 \
         MICROPY_VFS_LFS2=1 \
         FROZEN_MANIFEST=/Users/Luppy/PineTime/wasp-os/wasp/boards/pinetime/manifest.py
   make[1]: Entering directory '/Users/Luppy/PineTime/wasp-os/micropython/ports/nrf'
   python3 ../../py/makeversionhdr.py build-pinetime-s132/genhdr/mpversion.h
   GEN build-pinetime-s132/genhdr/qstr.i.last
   arm-none-eabi-gcc -E -DNO_QSTR -Ibuild-pinetime-s132/tmp -DBLUETOOTH_SD_DEBUG=1 -DBLUETOOTH_SD=132 -flto -mthumb -mabi=aapcs -fsingle-precision-constant -Wdouble-promotion -mtune=cortex-m4 -mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -mfloat-abi=hard -Idrivers/bluetooth/s132_nrf52_6.1.1/s132_nrf52_6.1.1_API/include -Idrivers/bluetooth/s132_nrf52_6.1.1/s132_nrf52_6.1.1_API/include/nrf52 -I. -I../.. -Ibuild-pinetime-s132 -I./../../lib/cmsis/inc -I./modules/machine -I./modules/ubluepy -I./modules/music -I./modules/random -I./modules/ble -I./modules/board -I../../lib/mp-readline -I./drivers/bluetooth -I./drivers -I../../lib/nrfx/ -I../../lib/nrfx/drivers -I../../lib/nrfx/drivers/include -I../../lib/nrfx/mdk -I../../lib/nrfx/hal -I../../lib/nrfx/drivers/src/ -Wall -Werror -g -ansi -std=c11 -nostdlib  -DNRF52832_XXAA -DNRF52 -DNRF52832 -DCONFIG_GPIO_AS_PINRESET -DFFCONF_H=\"lib/oofatfs/ffconf.h\" -DMICROPY_VFS_LFS2=1 -DLFS2_NO_MALLOC -DLFS2_NO_DEBUG -DLFS2_NO_WARN -DLFS2_NO_ERROR -DLFS2_NO_ASSERT -fno-strict-aliasing -Iboards/pinetime -DNRF5_HAL_H='<nrf52_hal.h>' -Os -DNDEBUG -DMICROPY_MODULE_FROZEN_STR -DMICROPY_QSTR_EXTRA_POOL=mp_qstr_frozen_const_pool -DMICROPY_MODULE_FROZEN_MPY ../../lib/littlefs/lfs2.c ../../lib/littlefs/lfs2_util.c ../../py/mpstate.c ../../py/malloc.c ../../py/gc.c ../../py/pystack.c ../../py/qstr.c ../../py/vstr.c ../../py/mpprint.c ../../py/unicode.c ../../py/mpz.c ../../py/reader.c ../../py/lexer.c ../../py/parse.c ../../py/scope.c ../../py/compile.c ../../py/emitcommon.c ../../py/emitbc.c ../../py/asmbase.c ../../py/asmx64.c ../../py/emitnx64.c ../../py/asmx86.c ../../py/emitnx86.c ../../py/asmthumb.c ../../py/emitnthumb.c ../../py/emitinlinethumb.c ../../py/asmarm.c ../../py/emitnarm.c ../../py/asmxtensa.c ../../py/emitnxtensa.c ../../py/emitinlinextensa.c ../../py/emitnxtensawin.c ../../py/formatfloat.c ../../py/parsenumbase.c ../../py/parsenum.c ../../py/emitglue.c ../../py/persistentcode.c ../../py/runtime.c ../../py/runtime_utils.c ../../py/scheduler.c ../../py/nativeglue.c ../../py/ringbuf.c ../../py/stackctrl.c ../../py/argcheck.c ../../py/warning.c ../../py/profile.c ../../py/map.c ../../py/obj.c ../../py/objarray.c ../../py/objattrtuple.c ../../py/objbool.c ../../py/objboundmeth.c ../../py/objcell.c ../../py/objclosure.c ../../py/objcomplex.c ../../py/objdeque.c ../../py/objdict.c ../../py/objenumerate.c ../../py/objexcept.c ../../py/objfilter.c ../../py/objfloat.c ../../py/objfun.c ../../py/objgenerator.c ../../py/objgetitemiter.c ../../py/objint.c ../../py/objint_longlong.c ../../py/objint_mpz.c ../../py/objlist.c ../../py/objmap.c ../../py/objmodule.c ../../py/objobject.c ../../py/objpolyiter.c ../../py/objproperty.c ../../py/objnone.c ../../py/objnamedtuple.c ../../py/objrange.c ../../py/objreversed.c ../../py/objset.c ../../py/objsingleton.c ../../py/objslice.c ../../py/objstr.c ../../py/objstrunicode.c ../../py/objstringio.c ../../py/objtuple.c ../../py/objtype.c ../../py/objzip.c ../../py/opmethods.c ../../py/sequence.c ../../py/stream.c ../../py/binary.c ../../py/builtinimport.c ../../py/builtinevex.c ../../py/builtinhelp.c ../../py/modarray.c ../../py/modbuiltins.c ../../py/modcollections.c ../../py/modgc.c ../../py/modio.c ../../py/modmath.c ../../py/modcmath.c ../../py/modmicropython.c ../../py/modstruct.c ../../py/modsys.c ../../py/moduerrno.c ../../py/modthread.c ../../py/vm.c ../../py/bc.c ../../py/showbc.c ../../py/repl.c ../../py/smallint.c ../../py/frozenmod.c ../../extmod/moductypes.c ../../extmod/modujson.c ../../extmod/modure.c ../../extmod/moduzlib.c ../../extmod/moduheapq.c ../../extmod/modutimeq.c ../../extmod/moduhashlib.c ../../extmod/moducryptolib.c ../../extmod/modubinascii.c ../../extmod/virtpin.c ../../extmod/machine_mem.c ../../extmod/machine_pinbase.c ../../extmod/machine_signal.c ../../extmod/machine_pulse.c ../../extmod/machine_i2c.c ../../extmod/machine_spi.c ../../extmod/modbluetooth.c ../../extmod/modussl_axtls.c ../../extmod/modussl_mbedtls.c ../../extmod/modurandom.c ../../extmod/moduselect.c ../../extmod/moduwebsocket.c ../../extmod/modwebrepl.c ../../extmod/modframebuf.c ../../extmod/vfs.c ../../extmod/vfs_blockdev.c ../../extmod/vfs_reader.c ../../extmod/vfs_posix.c ../../extmod/vfs_posix_file.c ../../extmod/vfs_fat.c ../../extmod/vfs_fat_diskio.c ../../extmod/vfs_fat_file.c ../../extmod/vfs_lfs.c ../../extmod/utime_mphal.c ../../extmod/uos_dupterm.c ../../lib/embed/abort_.c ../../lib/utils/printf.c build-pinetime-s132/genhdr/moduledefs.h main.c mphalport.c help.c gccollect.c pin_named_pins.c fatfs_port.c drivers/flash.c drivers/softpwm.c drivers/ticker.c drivers/wdt.c drivers/bluetooth/ble_drv.c drivers/bluetooth/ble_uart.c device/startup_nrf52832.c ../../lib/libm/math.c ../../lib/libm/fmodf.c ../../lib/libm/nearbyintf.c ../../lib/libm/ef_sqrt.c ../../lib/libm/kf_rem_pio2.c ../../lib/libm/kf_sin.c ../../lib/libm/kf_cos.c ../../lib/libm/kf_tan.c ../../lib/libm/ef_rem_pio2.c ../../lib/libm/sf_sin.c ../../lib/libm/sf_cos.c ../../lib/libm/sf_tan.c ../../lib/libm/sf_frexp.c ../../lib/libm/sf_modf.c ../../lib/libm/sf_ldexp.c ../../lib/libm/asinfacosf.c ../../lib/libm/atanf.c ../../lib/libm/atan2f.c ../../lib/libc/string0.c ../../lib/mp-readline/readline.c ../../lib/utils/pyexec.c ../../lib/utils/sys_stdio_mphal.c ../../lib/utils/interrupt_char.c ../../lib/timeutils/timeutils.c modules/machine/modmachine.c modules/machine/uart.c modules/machine/spi.c modules/machine/i2c.c modules/machine/adc.c modules/machine/pin.c modules/machine/timer.c modules/machine/rtcounter.c modules/machine/pwm.c modules/machine/temp.c modules/uos/moduos.c modules/uos/microbitfs.c modules/utime/modutime.c modules/board/modboard.c modules/board/led.c modules/ubluepy/modubluepy.c modules/ubluepy/ubluepy_peripheral.c modules/ubluepy/ubluepy_service.c modules/ubluepy/ubluepy_characteristic.c modules/ubluepy/ubluepy_uuid.c modules/ubluepy/ubluepy_delegate.c modules/ubluepy/ubluepy_constants.c modules/ubluepy/ubluepy_descriptor.c modules/ubluepy/ubluepy_scanner.c modules/ubluepy/ubluepy_scan_entry.c modules/music/modmusic.c modules/music/musictunes.c modules/ble/modble.c modules/random/modrandom.c ../../py/mpconfig.h mpconfigport.h >build-pinetime-s132/genhdr/qstr.i.last
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../py/mpprint.c:33:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../py/asmthumb.c:38:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../py/modbuiltins.c:231:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../py/modmicropython.c:33:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../extmod/machine_pulse.h:30,
                  from ../../extmod/machine_pulse.c:29:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../extmod/machine_i2c.c:32:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../extmod/machine_spi.h:30,
                  from ../../extmod/machine_spi.c:31:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../extmod/modbluetooth.c:36:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../extmod/utime_mphal.c:34:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../lib/utils/printf.c:34:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ../../lib/nrfx/hal/nrf_gpio.h:35,
                  from ./pin_defs_nrf5.h:31,
                  from ./modules/machine/pin.h:33,
                  from ./modules/machine/uart.h:31,
                  from main.c:48:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from mphalport.c:30:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from pin_named_pins.c:31:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ../../lib/nrfx/drivers/include/nrfx_nvmc.h:35,
                  from ./drivers/flash.h:30,
                  from drivers/flash.c:31:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from drivers/softpwm.c:27:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from drivers/ticker.c:27:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from drivers/wdt.c:27:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   drivers/bluetooth/ble_drv.c:36:10: fatal error: nrf_sdm.h: No such file or directory
   #include "nrf_sdm.h"
            ^~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from drivers/bluetooth/ble_uart.c:32:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../lib/mp-readline/readline.c:33:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../lib/utils/pyexec.c:37:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from ../../lib/utils/sys_stdio_mphal.c:33:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/machine/modmachine.c:32:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/machine/uart.c:37:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/machine/spi.c:37:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/machine/i2c.c:33:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/machine/adc.c:32:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/machine/pin.c:35:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ../../lib/nrfx/drivers/include/nrfx_timer.h:35,
                  from modules/machine/timer.c:30:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ../../lib/nrfx/drivers/include/nrfx_rtc.h:35,
                  from modules/machine/rtcounter.c:32:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/machine/pwm.c:32:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/machine/temp.c:32:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ../../lib/nrfx/hal/nrf_gpio.h:35,
                  from ./pin_defs_nrf5.h:31,
                  from ./modules/machine/pin.h:33,
                  from ./modules/machine/uart.h:31,
                  from modules/uos/moduos.c:42:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ../../lib/nrfx/drivers/include/nrfx_nvmc.h:35,
                  from ./drivers/flash.h:30,
                  from modules/uos/microbitfs.c:33:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ../../lib/nrfx/hal/nrf_gpio.h:35,
                  from ./pin_defs_nrf5.h:31,
                  from ./modules/machine/pin.h:33,
                  from modules/board/modboard.c:33:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from modules/board/led.c:30:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from modules/ubluepy/ubluepy_scanner.c:36:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/music/modmusic.c:27:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ./mphalport.h:31,
                  from ../../py/mphal.h:34,
                  from modules/music/musictunes.c:32:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   In file included from ../../lib/nrfx/nrfx.h:37:0,
                  from ../../lib/nrfx/hal/nrf_rng.h:35,
                  from modules/random/modrandom.c:35:
   ./nrfx_glue.h:42:10: fatal error: nrf_nvic.h: No such file or directory
   #include "nrf_nvic.h"
            ^~~~~~~~~~~~
   compilation terminated.
   make[1]: *** [../../py/mkrules.mk:76: build-pinetime-s132/genhdr/qstr.i.last] Error 1
   make[1]: *** Deleting file 'build-pinetime-s132/genhdr/qstr.i.last'
   make[1]: Leaving directory '/Users/Luppy/PineTime/wasp-os/micropython/ports/nrf'
   make: *** [Makefile:40: micropython] Error 2

   # Luppy at Luppys-MacBook-Pro.local in ~/PineTime/wasp-os on git:master ● [2:36:55]
   → find . -name nrf_nvic.h                              
   ./bootloader/lib/softdevice/s132_nrf52_6.1.1/s132_nrf52_6.1.1_API/include/nrf_nvic.h
   ./bootloader/lib/softdevice/s140_nrf52_6.1.1/s140_nrf52_6.1.1_API/include/nrf_nvic.h
   ./bootloader/lib/tinyusb/hw/mcu/nordic/nrf5x/s140_nrf52_6.1.1_API/include/nrf_nvic.h
   ./micropython/lib/tinyusb/hw/mcu/nordic/nrf5x/s140_nrf52_6.1.1_API/include/nrf_nvic.h

   # Luppy at Luppys-MacBook-Pro.local in ~/PineTime/wasp-os on git:master ● [2:37:02]
   → 

Watch Application System in Python
==================================

Introduction
------------

Currently in its infancy wasp-os provides only a little more than a simple
digital clock application for `PineTime <https://www.pine64.org/pinetime/>`_
together with access to the MicroPython REPL for interactive testing and
tweaking. However it keeps time well and has enough power saving
functions implemented that it can survive for well over 72 hours between
charges so even at this early stage it is functional as a wearable
timepiece.

Wasp-os includes a robust bootloader based on the Adafruit NRF52
Bootloader. It has been extended to make it robust for development on
form-factor devices without a reset button, power switch, SWD debugger
or UART. This allows us to confidently develop on sealed devices relying
only on BLE for updates.

Videos
------

.. image:: https://img.youtube.com/vi/YktiGUSRJB4/0.jpg
   :target: https://www.youtube.com/watch?v=YktiGUSRJB4
   :alt: An M2 pre-release running on Pine64 PineTime

`An M2 pre-release running on Pine64 PineTime <https://www.youtube.com/watch?v=YktiGUSRJB4>`_

.. image:: https://img.youtube.com/vi/tuk9Nmr3Jo8/0.jpg
   :target: https://www.youtube.com/watch?v=tuk9Nmr3Jo8
   :alt: How to develop wasp-os python applications on a Pine64 PineTime

`How to develop wasp-os python applications on a Pine64 PineTime <https://www.youtube.com/watch?v=tuk9Nmr3Jo8>`_

.. image:: https://img.youtube.com/vi/kf1VHj587Mc/0.jpg
   :target: https://www.youtube.com/watch?v=kf1VHj587Mc
   :alt: Developing for Pine64 PineTime using wasp-os and MicroPython

`Developing for Pine64 PineTime using wasp-os and MicroPython <https://www.youtube.com/watch?v=kf1VHj587Mc>`_

Documentation
-------------

Wasp-os is has `extensive documentation <https://wasp-os.readthedocs.io>`_
which includes a detailed `Applicaiton Writer's Guide
<https://daniel-thompson.github.io/wasp-os/appguide.html>`_ to help you
get started coding for wasp-os as quickly as possible.

Building from a git clone
-------------------------

Get the code from
`https://github.com/daniel-thompson/wasp-os <https://github.com/daniel-thompson/wasp-os>`_ .

.. code-block:: sh

   pip3 install --user click serial pyserial
   make submodules
   make softdevice
   make -j `nproc` BOARD=pinetime all

.. note::

    You will need a toolchain for the Arm Cortex-M4. wasp-os is developed and
    tested using the `GNU-RM toolchain
    <https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm>`_
    (9-2019-q4) from Arm.

    There are known problems with toolchains older than gcc-7.3 due to problems
    with link-time-optimization (which is enabled by default).

Installing
----------

Use an SWD programmer to install ``bootloader.hex`` to the PineTime.  This
file is an Intel HEX file containing both the bootloader and the Nordic
SoftDevice. Be careful to disconnect cleanly from the debug software
since just pulling out the SWD cable will mean the nRF52 will still
believe it is being debugged (and won't properly enter deep sleep
modes).

.. note::

    If you have a new PineTime then it will have been delivered with flash
    protection enabled. You must disable the flash protection before trying to
    program it.

To install using Android device:

* Copy ``micropython.zip`` to your Android device and download nRF Connect
  for Android if you do not already have it.
* In nRF Connect, choose settings and reduce the DFU packet count from
  10 to 4.
* Connect to PineDFU using nRFConnect, click the DFU button and send
  ``micropython.zip`` to the device.

To install using Linux and ota-dfu:

* Look up the MAC address for your watch (try: ``sudo hcitool lescan``\ ).
* Use ota-dfu to upload ``micropython.zip`` to the device. For example:
  ``tools/ota-dfu/dfu.py -z micropython.zip -a A0:B1:C2:D3:E3:F5 --legacy``

At the end of this process your watch will show the time (03:00) together
with a date and battery meter. When the watch goes into power saving mode
you can use the side button to wake it again.

At this point you will also be able to use the Nordic UART Service to
access the MicroPython REPL, although currently you must send ^C to
interrupt the program that updates the watch display. You can use 
``tools/wasptool --console`` to access the MicroPython REPL.

To set the time and restart the main application:

.. code-block:: python

   ^C
   watch.rtc.set_localtime((yyyy, mm, dd, HH, MM, SS))
   wasp.system.run()

Or just use:

.. code-block:: sh

   ./tools/wasptool --rtc

which can run these commands automatically.

As mentioned above there are many drivers and features still to be
developed, see the `TODO list <TODO.md>`_ for current status.

Screenshots
-----------

.. image:: res/clock_app.jpg
   :alt: wasp-os digital clock app running on PineTime
