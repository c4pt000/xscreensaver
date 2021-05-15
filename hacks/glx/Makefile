# hacks/glx/Makefile.in --- xscreensaver, Copyright © 1999-2021 Jamie Zawinski.
# the `../../configure' script generates `hacks/glx/Makefile' from this file.


.SUFFIXES:
.SUFFIXES: .c .o

srcdir		= .

top_srcdir	= ../..
top_builddir	= ..

install_prefix	=
prefix		= /usr
exec_prefix	= ${prefix}
bindir		= ${exec_prefix}/bin
datarootdir	= ${prefix}/share
datadir		= ${datarootdir}
mandir		= ${datarootdir}/man
libexecdir	= ${exec_prefix}/libexec
mansuffix	= 6
manNdir		= $(mandir)/man$(mansuffix)

HACKDIR		= ${libexecdir}/xscreensaver
HACK_CONF_DIR	= ${datadir}/xscreensaver/config

CC		= gcc -std=gnu89 -pedantic -Wall -Wnested-externs -Wstrict-prototypes -Wmissing-prototypes -Wdeclaration-after-statement -Wno-overlength-strings -Wno-language-extension-token -Wno-variadic-macros
CFLAGS		= 
LDFLAGS		=  -L${exec_prefix}/lib64
DEFS		= -DSTANDALONE -DUSE_GL -DHAVE_CONFIG_H
LIBS		= 
PERL		= /usr/bin/perl

THREAD_LIBS	= -lpthread
THREAD_CFLAGS	= -pthread

DEPEND		= makedepend
DEPEND_FLAGS	= 
DEPEND_DEFINES	= 

SHELL		= /bin/sh
INSTALL		= /usr/bin/install -c
SUID_FLAGS      = -o root -m 4755
INSTALL_PROGRAM = ${INSTALL}
INSTALL_SETUID	= $(INSTALL_PROGRAM) $(SUID_FLAGS)
INSTALL_DATA	= ${INSTALL} -m 644
INSTALL_DIRS	= ${INSTALL} -d
PROG_SETCAP	= 
SETCAP_FLAGS	= cap_net_raw=p

X_CFLAGS	= 
X_LIBS		= 
X_PRE_LIBS	=  -lSM -lICE
X_EXTRA_LIBS	= 
XFT_LIBS	= -lXft 

# Note: see comment in ../../driver/Makefile.in for explanation of X_LIBS, etc.
#
HACK_PRE	= $(LIBS) $(X_LIBS)
HACK_POST     = $(X_PRE_LIBS) $(XFT_LIBS) -lXt -lX11 -lXext $(X_EXTRA_LIBS) -lm
HACK_POST2	= -lEGL -lGLU -lGL   $(HACK_POST)
HACK_LIBS	= $(HACK_PRE)            $(HACK_POST2)
PNG_LIBS	= $(HACK_PRE)            -lgdk_pixbuf_xlib-2.0 -lgdk_pixbuf-2.0 -lX11 -lgio-2.0 -lgobject-2.0 -lglib-2.0  $(HACK_POST2)
GLE_LIBS	= $(HACK_PRE) -lgle -lgdk_pixbuf_xlib-2.0 -lgdk_pixbuf-2.0 -lX11 -lgio-2.0 -lgobject-2.0 -lglib-2.0  $(HACK_POST2)
TEXT_LIBS	= -lutil
#### Is LIBCAP_CFLAGS necessary?
LIBCAP_CFLAGS	= 
LIBCAP_LIBS	= 

HACK_SRC	= $(srcdir)/..
HACK_BIN	= ..
UTILS_SRC	= $(HACK_SRC)/../utils
JWXYZ_SRC	= $(HACK_SRC)/../jwxyz
UTILS_BIN	= $(HACK_BIN)/../utils
JWXYZ_BIN	= $(HACK_BIN)/../jwxyz

INCLUDES_1	= -I. -I$(srcdir) -I$(UTILS_SRC) -I$(JWXYZ_SRC) -I$(HACK_SRC) -I$(HACK_BIN) -I../..
INCLUDES	= $(INCLUDES_1)   -I/usr/include/gtk-2.0 -I/usr/lib64/gtk-2.0/include -I/usr/include/pango-1.0 -I/usr/include/glib-2.0 -I/usr/lib64/glib-2.0/include -I/usr/include/sysprof-4 -I/usr/include/harfbuzz -I/usr/include/freetype2 -I/usr/include/libpng16 -I/usr/include/libmount -I/usr/include/blkid -I/usr/include/fribidi -I/usr/include/libxml2 -I/usr/include/cairo -I/usr/include/pixman-1 -I/usr/include/gdk-pixbuf-2.0 -I/usr/include/atk-1.0 -pthread  -I/usr/include/gdk-pixbuf-2.0 -I/usr/include/glib-2.0 -I/usr/lib64/glib-2.0/include -I/usr/include/sysprof-4 -I/usr/include/libpng16 -I/usr/include/libmount -I/usr/include/blkid -pthread  -I/usr/include/freetype2 -I/usr/include/libpng16 -I/usr/include/harfbuzz -I/usr/include/glib-2.0 -I/usr/lib64/glib-2.0/include -I/usr/include/sysprof-4 -I/usr/include/libxml2 -pthread 

UTILDIR_OBJS	= $(UTILS_BIN)/colors.o $(UTILS_BIN)/grabclient.o \
		  $(UTILS_BIN)/hsv.o $(UTILS_BIN)/resources.o \
		  $(UTILS_BIN)/usleep.o $(UTILS_BIN)/visual.o \
		  $(UTILS_BIN)/xmu.o $(UTILS_BIN)/xft.o \
		  $(UTILS_BIN)/utf8wc.o $(UTILS_BIN)/logo.o \
		  $(UTILS_BIN)/visual-gl.o \
		  $(UTILS_BIN)/yarandom.o $(UTILS_BIN)/xshm.o \
		  $(UTILS_BIN)/textclient.o $(UTILS_BIN)/async_netdb.o \
		  $(UTILS_BIN)/aligned_malloc.o $(UTILS_BIN)/thread_util.o \
		  $(UTILS_BIN)/spline.o $(UTILS_BIN)/pow2.o \
		  $(UTILS_BIN)/font-retry.o
JWXYZ_OBJS	= $(JWXYZ_BIN)/jwzgles.o
HACKDIR_OBJS	= $(HACK_BIN)/screenhack.o $(HACK_BIN)/xlockmore.o \
		  $(HACK_BIN)/fps.o $(HACK_BIN)/ximage-loader.o
PNG		= $(HACK_BIN)/ximage-loader.o

SRCS		= xscreensaver-gl-visual.c normals.c erase-gl.c fps-gl.c \
		  atlantis.c b_draw.c b_lockglue.c b_sphere.c bubble3d.c \
		  buildlwo.c cage.c dolphin.c gears.c lament.c lament_model.c \
		  moebius.c morph3d.c pipeobjs.c pipes.c rubik.c s1_1.c s1_2.c \
		  s1_3.c s1_4.c s1_5.c s1_6.c s1_b.c shark.c sproingies.c \
		  sproingiewrap.c stairs.c superquadrics.c swim.c whale.c \
		  xlock-gl-utils.c glplanet.c pulsar.c \
		  extrusion.c extrusion-helix2.c extrusion-helix3.c \
		  extrusion-helix4.c extrusion-joinoffset.c extrusion-screw.c \
		  extrusion-taper.c extrusion-twistoid.c sierpinski3d.c \
		  gflux.c stonerview.c stonerview-move.c stonerview-osc.c \
		  stonerview-view.c starwars.c glut_stroke.c glut_swidth.c \
		  gltext.c molecule.c dangerball.c sphere.c tube.c circuit.c \
		  menger.c engine.c flipscreen3d.c dnalogo.c \
		  grab-ximage.c glsnake.c boxed.c glforestfire.c sballs.c \
		  cubenetic.c spheremonics.c marching.c lavalite.c rotator.c \
		  trackball.c gltrackball.c queens.c endgame.c chessmodels.c \
		  glblur.c gllist.c flurry.c flurry-smoke.c flurry-spark.c \
		  flurry-star.c flurry-texture.c atunnel.c tunnel_draw.c \
		  flyingtoasters.c toaster.c toaster_base.c toaster_handle.c \
		  toaster_handle2.c toaster_jet.c toaster_knob.c \
		  toaster_slots.c toaster_wing.c toast.c toast2.c \
		  bouncingcow.c cow_face.c cow_hide.c cow_hoofs.c cow_horns.c \
		  cow_tail.c cow_udder.c glslideshow.c jigglypuff.c klein.c \
		  hypertorus.c glmatrix.c cubestorm.c glknots.c blocktube.c \
		  flipflop.c antspotlight.c polytopes.c gleidescope.c \
		  mirrorblob.c blinkbox.c noof.c polyhedra.c polyhedra-gl.c \
		  antinspect.c providence.c pinion.c involute.c boing.c \
		  texfont.c carousel.c fliptext.c antmaze.c \
		  tangram.c tangram_shapes.c crackberg.c glhanoi.c cube21.c \
		  timetunnel.c juggler3d.c topblock.c glschool.c \
		  glschool_gl.c glschool_alg.c glcells.c voronoi.c \
		  moebiusgears.c lockward.c cubicgrid.c hypnowheel.c \
		  skytentacles.c teapot.c sonar.c sonar-sim.c sonar-icmp.c \
		  jigsaw.c photopile.c dropshadow.c rubikblocks.c surfaces.c \
		  hilbert.c companion.c companion_quad.c companion_disc.c \
		  companion_heart.c tronbit.c tronbit_idle1.c tronbit_idle2.c \
		  tronbit_no.c tronbit_yes.c kaleidocycle.c \
		  quasicrystal.c unknownpleasures.c geodesic.c geodesicgears.c \
		  projectiveplane.c winduprobot.c robot.c robot-wireframe.c \
		  cityflow.c romanboy.c splitflap.c splitflap_obj.c \
		  dymaxionmap.c dymaxionmap-coords.c unicrud.c energystream.c \
		  raverhoop.c hydrostat.c discoball.c cubetwist.c cubestack.c \
		  splodesic.c hexstrut.c vigilance.c seccam.c esper.c \
		  razzledazzle.c ships.c peepers.c crumbler.c quickhull.c \
		  maze3d.c handsy.c handsy_model.c gravitywell.c deepstars.c \
		  gibson.c etruscanvenus.c sphereeversion.c covid19.c \
		  co____9.c headroom.c headroom_model.c beats.c glsl-utils.c

OBJS		= xscreensaver-gl-visual.o normals.o erase-gl.o fps-gl.o \
		  atlantis.o b_draw.o b_lockglue.o b_sphere.o bubble3d.o \
		  buildlwo.o cage.o dolphin.o gears.o lament.o lament_model.o \
		  moebius.o morph3d.o pipeobjs.o pipes.o rubik.o s1_1.o s1_2.o \
		  s1_3.o s1_4.o s1_5.o s1_6.o s1_b.o shark.o sproingies.o \
		  sproingiewrap.o stairs.o superquadrics.o swim.o whale.o \
		  xlock-gl-utils.o glplanet.o pulsar.o \
		  extrusion.o extrusion-helix2.o extrusion-helix3.o \
		  extrusion-helix4.o extrusion-joinoffset.o extrusion-screw.o \
		  extrusion-taper.o extrusion-twistoid.o sierpinski3d.o \
		  gflux.o stonerview.o stonerview-move.o stonerview-osc.o \
		  stonerview-view.o starwars.o glut_stroke.o glut_swidth.o \
		  gltext.o molecule.o dangerball.o sphere.o tube.o circuit.o \
		  menger.o engine.o flipscreen3d.o dnalogo.o \
	          grab-ximage.o glsnake.o boxed.o glforestfire.o sballs.o \
		  cubenetic.o spheremonics.o marching.o lavalite.o rotator.o \
		  trackball.o gltrackball.o queens.o endgame.o chessmodels.o \
		  glblur.o gllist.o flurry.o flurry-smoke.o flurry-spark.o \
		  flurry-star.o flurry-texture.o atunnel.o tunnel_draw.o \
		  flyingtoasters.o toaster.o toaster_base.o toaster_handle.o \
		  toaster_handle2.o toaster_jet.o toaster_knob.o \
		  toaster_slots.o toaster_wing.o toast.o toast2.o \
		  bouncingcow.o cow_face.o cow_hide.o cow_hoofs.o cow_horns.o \
		  cow_tail.o cow_udder.o glslideshow.o jigglypuff.o klein.o \
		  hypertorus.o glmatrix.o cubestorm.o glknots.o blocktube.o \
		  flipflop.o antspotlight.o polytopes.o gleidescope.o \
		  mirrorblob.o blinkbox.o noof.o polyhedra.o polyhedra-gl.o \
		  antinspect.o providence.o pinion.o involute.o boing.o \
		  texfont.o texfont-glsl.o carousel.o fliptext.o antmaze.o \
		  tangram.o tangram_shapes.o crackberg.o glhanoi.o cube21.o \
		  timetunnel.o juggler3d.o topblock.o glschool.o \
		  glschool_gl.o glschool_alg.o glcells.o voronoi.o \
		  moebiusgears.o lockward.o cubicgrid.o hypnowheel.o \
		  skytentacles.o teapot.o sonar.o sonar-sim.o sonar-icmp.o \
		  jigsaw.o photopile.o dropshadow.o rubikblocks.o surfaces.o \
		  hilbert.o companion.o companion_quad.o companion_disc.o \
		  companion_heart.o tronbit.o tronbit_idle1.o tronbit_idle2.o \
		  tronbit_no.o tronbit_yes.o kaleidocycle.o \
		  quasicrystal.o unknownpleasures.o geodesic.o geodesicgears.o \
		  projectiveplane.o winduprobot.o robot.o robot-wireframe.o \
		  cityflow.o romanboy.o splitflap.o splitflap_obj.o \
		  dymaxionmap.o dymaxionmap-coords.o unicrud.o energystream.o \
		  raverhoop.o hydrostat.o discoball.o cubetwist.o cubestack.o \
		  splodesic.o hexstrut.o vigilance.o seccam.o esper.o \
		  razzledazzle.o ships.o peepers.o crumbler.o quickhull.o \
		  maze3d.o handsy.o handsy_model.o gravitywell.o deepstars.o \
		  gibson.o etruscanvenus.o sphereeversion.o covid19.o \
		  headroom.o headroom_model.o beats.o glsl-utils.o

GL_EXES		= cage gears moebius pipes sproingies stairs superquadrics \
		  morph3d rubik atlantis lament bubble3d glplanet pulsar \
		  sierpinski3d gflux stonerview starwars gltext molecule \
		  dangerball circuit menger engine flipscreen3d glsnake boxed \
		  sballs cubenetic spheremonics lavalite queens \
		  endgame glblur flurry atunnel flyingtoasters bouncingcow \
		  glslideshow jigglypuff klein hypertorus glmatrix cubestorm \
		  glknots blocktube flipflop antspotlight polytopes \
		  gleidescope mirrorblob blinkbox noof polyhedra \
		  antinspect providence pinion boing carousel fliptext \
		  antmaze tangram crackberg glhanoi cube21 timetunnel \
		  juggler3d topblock glschool glcells voronoi moebiusgears \
		  lockward cubicgrid hypnowheel skytentacles jigsaw photopile \
		  rubikblocks surfaces hilbert companioncube tronbit \
		  kaleidocycle quasicrystal unknownpleasures geodesic \
		  geodesicgears projectiveplane winduprobot cityflow romanboy \
		  splitflap dymaxionmap unicrud energystream raverhoop \
		  hydrostat discoball cubetwist cubestack splodesic \
		  hexstrut vigilance esper razzledazzle peepers crumbler \
		  maze3d handsy gravitywell deepstars gibson etruscanvenus \
		  sphereeversion covid19 headroom beats
GLE_EXES	= extrusion
SUID_EXES	= sonar
SETCAP_EXES	= sonar
GL_UTIL_EXES	= xscreensaver-gl-visual
JWZGLES_OBJS	= 
HACK_EXES_1	= $(GL_EXES) $(GLE_EXES)
HACK_EXES	= $(HACK_EXES_1) $(SUID_EXES)
XSHM_OBJS	= $(UTILS_BIN)/xshm.o $(UTILS_BIN)/aligned_malloc.o
GRAB_OBJS	= $(UTILS_BIN)/grabclient.o grab-ximage.o $(XSHM_OBJS)
ANIM_OBJS	= recanim-gl.o
ANIM_LIBS	= -lgdk_pixbuf_xlib-2.0 -lgdk_pixbuf-2.0 -lX11 -lgio-2.0 -lgobject-2.0 -lglib-2.0 
EXES		= $(GL_UTIL_EXES) $(HACK_EXES)

RETIRED_EXES	= $(RETIRED_GL_EXES)
RETIRED_GL_EXES	= glforestfire

FPS_OBJS	= texfont.o $(HACK_BIN)/fps.o fps-gl.o \
		  
HACK_GLSL_OBJS  = glsl-utils.o
HACK_OBJS	= $(HACK_BIN)/screenhack.o $(HACK_BIN)/xlockmore.o \
		  xlock-gl-utils.o erase-gl.o \
		  $(UTILS_BIN)/resources.o \
		  $(UTILS_BIN)/colors.o \
		  $(UTILS_BIN)/hsv.o \
		  $(UTILS_BIN)/visual.o \
		  $(UTILS_BIN)/visual-gl.o \
		  $(UTILS_BIN)/font-retry.o \
		  $(UTILS_BIN)/pow2.o \
		  $(UTILS_BIN)/utf8wc.o \
		  $(UTILS_BIN)/usleep.o \
		  $(UTILS_BIN)/xmu.o \
		  $(UTILS_BIN)/yarandom.o \
		  ${FPS_OBJS} $(JWZGLES_OBJS) $(HACK_GLSL_OBJS) 

HDRS		= atlantis.h bubble3d.h buildlwo.h e_textures.h \
		  grab-ximage.h tube.h sphere.h boxed.h \
		  stonerview.h stonerview-move.h stonerview-osc.h \
		  glutstroke.h glut_roman.h glut_mroman.h marching.h \
		  rotator.h trackball.h gltrackball.h chessmodels.h \
		  chessgames.h gllist.h flurry.h tunnel_draw.h ants.h \
		  polyhedra.h normals.h texfont.h tangram_shapes.h \
		  sproingies.h extrusion.h glschool.h glschool_gl.h \
		  glschool_alg.h topblock.h involute.h teapot.h sonar.h \
		  dropshadow.h starwars.h teapot2.h dnapizza.h curlicue.h \
		  quickhull.h dymaxionmap-coords.h handsy_anim.h \
		  glsl-utils.h
GL_MEN		= xscreensaver-gl-visual.man \
		  atlantis.man boxed.man bubble3d.man cage.man circuit.man \
		  cubenetic.man dangerball.man engine.man extrusion.man \
		  flipscreen3d.man gears.man gflux.man \
		  glplanet.man glsnake.man gltext.man lament.man lavalite.man \
		  menger.man moebius.man molecule.man morph3d.man pipes.man \
		  pulsar.man queens.man rubik.man sballs.man sierpinski3d.man \
		  spheremonics.man sproingies.man stairs.man starwars.man \
		  stonerview.man superquadrics.man \
		  endgame.man flurry.man glblur.man atunnel.man \
		  flyingtoasters.man bouncingcow.man glslideshow.man \
		  jigglypuff.man klein.man hypertorus.man glmatrix.man \
		  cubestorm.man glknots.man blocktube.man flipflop.man \
		  antspotlight.man polytopes.man gleidescope.man \
		  mirrorblob.man blinkbox.man noof.man polyhedra.man \
		  antinspect.man providence.man pinion.man boing.man \
		  carousel.man fliptext.man antmaze.man tangram.man \
		  crackberg.man glhanoi.man cube21.man timetunnel.man \
		  juggler3d.man topblock.man glschool.man glcells.man \
		  voronoi.man moebiusgears.man lockward.man cubicgrid.man \
		  hypnowheel.man skytentacles.man sonar.man jigsaw.man \
		  photopile.man rubikblocks.man surfaces.man hilbert.man \
		  companioncube.man tronbit.man kaleidocycle.man \
		  quasicrystal.man unknownpleasures.man geodesic.man \
		  geodesicgears.man projectiveplane.man winduprobot.man \
		  cityflow.man romanboy.man splitflap.man dymaxionmap.man \
		  unicrud.man energystream.man raverhoop.man hydrostat.man \
		  discoball.man cubetwist.man cubestack.man splodesic.man \
		  hexstrut.man vigilance.man esper.man razzledazzle.man \
		  peepers.man crumbler.man maze3d.man handsy.man \
		  gravitywell.man deepstars.man gibson.man etruscanvenus.man \
		  sphereeversion.man covid19.man headroom.man beats.man
MEN		= $(GL_MEN)
RETIRED_MEN	= glforestfire.man
EXTRAS		= README Makefile.in dxf2gl.pl vrml2gl.pl wfront2gl.pl \
		  molecules.sh starwars.txt zalgo.txt *.dxf

TARFILES	= $(SRCS) $(HDRS) $(GL_MEN) $(RETIRED_MEN) $(EXTRAS)


default: all
all: $(EXES) $(RETIRED_EXES)

install:   install-program    install-xml   install-man
uninstall: uninstall-program  uninstall-xml uninstall-man

install-strip:
	$(MAKE) INSTALL_PROGRAM='$(INSTALL_PROGRAM) -s' install

# the hacks, in $HACKDIR
install-program:: $(EXES)
	@exes="$(HACK_EXES_1) $(GL_UTIL_EXES)" ;				\
	 idir="$(install_prefix)$(HACKDIR)" ;				\
	 if [ "$$exes" != "" ]; then					\
	   if [ ! -d $$idir ]; then					\
	     $(INSTALL_DIRS) $$idir ;					\
	   fi ;								\
	   for program in $$exes; do					\
	     echo $(INSTALL_PROGRAM) $$program $$idir/$$program ;	\
		  $(INSTALL_PROGRAM) $$program $$idir/$$program ;	\
	   done ;							\
									\
	   exes="$(SUID_EXES)" ;					\
	   if [ yes = yes ]; then				\
	     sinst="$(INSTALL_SETUID)" ;				\
	   else								\
	     sinst="$(INSTALL_PROGRAM)" ;				\
	   fi ;								\
	   for program in $$exes; do					\
	     echo $$sinst $$program $$idir/$$program ;			\
	     if   $$sinst $$program $$idir/$$program ; then		\
	        true ;							\
	     elif [ yes = yes ]; then			\
	       echo $(INSTALL_PROGRAM) $$program $$idir/$$program ;	\
	       if   $(INSTALL_PROGRAM) $$program $$idir/$$program ; then\
	         echo "" ;						\
	         echo "WARNING: unable to install $$program setuid:"	\
	              "installed non-setuid instead." ;			\
	         echo "" ;						\
	       else							\
	         exit 1 ;						\
	       fi ;							\
	     else							\
	       exit 1 ;							\
	     fi ;							\
	   done ;							\
									\
	   exes="${SETCAP_EXES}" ;					\
	   if [ no = yes ]; then				\
	     for program in $$exes; do					\
	       echo $(PROG_SETCAP) $(SETCAP_FLAGS) $$idir/$$program ;	\
	       if   $(PROG_SETCAP) $(SETCAP_FLAGS) $$idir/$$program ; then \
	         true ;							\
	       else							\
	         echo "" ;						\
	         echo "WARNING: unable to setcap $$program" ;		\
	         echo "" ;						\
	       fi ;							\
	     done ;							\
	   fi ;								\
	 fi


# When installing man pages, we install "foo.man" as "foo.N" and update
# the .TH line in the installed file with one like
#
#     .TH XScreenSaver N "V.VV (DD-MMM-YYYY)" "X Version 11"
#
# where N is the manual section suffix.
#
install-man: $(MEN)
	@men="$(MEN)" ;							\
	U=$(UTILS_SRC)/version.h ;					\
	V=`sed -n 's/.*xscreensaver \([0-9]\.[^)]*)\).*/\1/p' < $$U` ;	\
	T=/tmp/xs$$$$.$(mansuffix) ;					\
	TH=".TH XScreenSaver $(mansuffix) \"$$V\" \"X Version 11\"" ;	\
	echo "installing man pages: $$TH" ;				\
									\
	if [ ! -d $(install_prefix)$(manNdir) ]; then			\
	  $(INSTALL_DIRS) $(install_prefix)$(manNdir) ;			\
	 fi ;								\
									\
	for man in $$men; do						\
	  instname=`echo $$man | sed 's/\.man$$/\.$(mansuffix)/'` ;	\
	  manbase=`echo $$man | sed 's/\.man$$//'` ;    \
	  TH=".TH $$manbase $(mansuffix) \"$$V\" \"X Version 11\" \"XScreenSaver manual\"" ;   \
	  sed -e "s/^\.TH.*/$$TH/"					\
	      -e 's@(MANSUFFIX)@($(mansuffix))@g'			\
	    < $(srcdir)/$$man > $$T ;					\
	  echo $(INSTALL_DATA) $(srcdir)/$$man				\
	   $(install_prefix)$(manNdir)/$$instname ;			\
	  $(INSTALL_DATA) $$T						\
	    $(install_prefix)$(manNdir)/$$instname ;			\
	done ;								\
	rm -f $$T

install-xml:
	@dest=$(install_prefix)$(HACK_CONF_DIR) ;			\
	 if [ ! -d $$dest ]; then					\
	   $(INSTALL_DIRS) $$dest ;					\
	 fi ;								\
	 src=$(srcdir)/../config ;					\
	 for file in $(EXES) $(SCRIPTS) ; do				\
	   if [ -f $$src/$$file.xml ]; then				\
	     echo $(INSTALL_DATA) $$src/$$file.xml $$dest/$$file.xml ;	\
	          $(INSTALL_DATA) $$src/$$file.xml $$dest/$$file.xml ;	\
	   fi ;								\
	done

# the hacks, in $HACKDIR
uninstall-program::
	@exes="$(HACK_EXES) $(RETIRED_EXES) $(GL_UTIL_EXES)" ;		\
	 idir="$(install_prefix)$(HACKDIR)" ;				\
	 for program in $$exes; do					\
	   echo rm -f $$idir/$$program ;				\
		rm -f $$idir/$$program ;				\
	 done

# $HACKDIR/xscreensaver-gl-visual used to be $bindir/xscreensaver-gl-helper
uninstall-program::
	rm -f $(install_prefix)$(bindir)/xscreensaver-gl-helper

uninstall-man:
	@men="$(MEN) $(RETIRED_MEN)" ;					\
	for man in $$men; do						\
	  instname=`echo $$man | sed 's/\.man$$/\.$(mansuffix)/'` ;	\
	  echo rm -f $(install_prefix)$(manNdir)/$$instname* ;		\
	       rm -f $(install_prefix)$(manNdir)/$$instname* ;		\
	done

uninstall-xml:
	@dest=$(install_prefix)$(HACK_CONF_DIR) ;			\
	 for file in $(EXES) $(RETIRED_EXES) $(SCRIPTS) ; do		\
	     echo rm -f $$dest/$$file.xml ;				\
	          rm -f $$dest/$$file.xml ;				\
	done

clean::
	-rm -f *.o a.out core $(EXES) $(RETIRED_EXES) molecules.h

distclean: clean
	-rm -f Makefile TAGS *~ "#"*

# Adds all current dependencies to Makefile
depend:
	$(DEPEND) -s '# DO NOT DELETE: updated by make depend'		    \
	$(DEPEND_FLAGS) --						    \
	$(INCLUDES) $(DEFS) $(DEPEND_DEFINES) $(CFLAGS) $(X_CFLAGS) --	    \
	$(SRCS)

# Adds some dependencies to Makefile.in -- not totally accurate, but pretty
# close.  This excludes dependencies on files in /usr/include, etc.  It tries
# to include only dependencies on files which are themselves a part of this
# package.
distdepend:: molecules.h
	@echo updating dependencies in `pwd`/Makefile.in... ;		    \
	$(DEPEND) -w 0 -f - 						    \
	-s '# DO NOT DELETE: updated by make distdepend' $(DEPEND_FLAGS) -- \
	$(INCLUDES_1) $(DEFS) $(DEPEND_DEFINES) $(CFLAGS) $(X_CFLAGS) --    \
	$(SRCS) 2>/dev/null |						    \
	sort -d |							    \
	(								    \
	  awk '/^# .*Makefile.in ---/,/^# DO .*distdepend/' < Makefile.in ; \
	  sed -e '/^#.*/d'						    \
	      -e 's@ \./@ @g;s@ /[^ ]*@@g;/^.*:$$/d'			    \
	      -e 's@\.\./\.\./utils@$$(UTILS_SRC)@g'			    \
	      -e 's@\.\./\.\./jwxyz@$$(JWXYZ_SRC)@g'			    \
	      -e 's@\.\./glx/@@g'					    \
	      -e 's@ \.\./@ $$(HACK_SRC)/@g'				    \
	      -e 's@ \([^$$]\)@ $$(srcdir)/\1@g'			    \
	      -e 's@ $$(srcdir)/\(.*config.h\)@ \1@g'			    \
	      -e 's@ $$(HACK_SRC)/\(.*config.h\)@ ../\1@g'		    \
	      -e 's@ $$(srcdir)/\(.*molecules.h\)@ \1@g'		    \
	      -e 's@ $$(srcdir)/\(images/gen/\)@ ../\1@g'		    \
	      -e 's@ $$(HACK_SRC)/\(images/gen/\)@ ../\1@g' ;		    \
	  echo ''							    \
	) > /tmp/distdepend.$$$$ &&					    \
	mv /tmp/distdepend.$$$$ Makefile.in


TAGS: tags
tags:
	find $(srcdir) -name '*.[chly]' -print | xargs etags -a

list_tarfiles:
	@find $(TARFILES) -type f -print | sort

check_men:
	@badmen="" ;							\
	 for exe in $(EXES); do						\
	   if ! [ -f $(srcdir)/$$exe.man ]; then			\
	     badmen="$$badmen $$exe" ;					\
	   fi ;								\
	 done ;								\
	 if [ -n "$$badmen" ]; then					\
	   echo "" ;							\
	   echo "Warning: The following programs have no manuals:" ;	\
	   echo "" ;							\
	   for m in $$badmen ; do					\
	     echo "    $$m" ;						\
	   done ;							\
	 fi

validate_xml:
	@echo "Validating XML..." ; \
	cd $(HACK_SRC) ; ./check-configs.pl $(GL_EXES) $(GLE_EXES) $(SUID_EXES)

distdepend:: check_men validate_xml



# Rules for noticing when the objects from the utils and hacks
# directories are out of date with respect to their sources, and going
# and building them according to the rules in their own Makefile...
#
$(UTILS_BIN)/colors.o:		$(UTILS_SRC)/colors.c
$(UTILS_BIN)/grabclient.o:	$(UTILS_SRC)/grabclient.c
$(UTILS_BIN)/hsv.o:		$(UTILS_SRC)/hsv.c
$(UTILS_BIN)/resources.o:	$(UTILS_SRC)/resources.c
$(UTILS_BIN)/usleep.o:		$(UTILS_SRC)/usleep.c
$(UTILS_BIN)/visual.o:		$(UTILS_SRC)/visual.c
$(UTILS_BIN)/xmu.o:		$(UTILS_SRC)/xmu.c
$(UTILS_BIN)/xft.o:		$(UTILS_SRC)/xft.c
$(UTILS_BIN)/utf8wc.o:		$(UTILS_SRC)/utf8wc.c
$(UTILS_BIN)/logo.o:		$(UTILS_SRC)/logo.c
$(UTILS_BIN)/visual-gl.o:	$(UTILS_SRC)/visual-gl.c
$(UTILS_BIN)/yarandom.o:	$(UTILS_SRC)/yarandom.c
$(UTILS_BIN)/xshm.o:		$(UTILS_SRC)/xshm.c
$(UTILS_BIN)/textclient.o:	$(UTILS_SRC)/textclient.c
$(UTILS_BIN)/async_netdb.o:	$(UTILS_SRC)/async_netdb.c
$(UTILS_BIN)/aligned_malloc.o:	$(UTILS_SRC)/aligned_malloc.c
$(UTILS_BIN)/thread_util.o:	$(UTILS_SRC)/thread_util.c
$(UTILS_BIN)/spline.o:		$(UTILS_SRC)/spline.c
$(UTILS_BIN)/pow2.o:		$(UTILS_SRC)/pow2.c
$(UTILS_BIN)/font-retry.o:	$(UTILS_SRC)/font-retry.c
$(HACK_BIN)/screenhack.o:	$(HACK_SRC)/screenhack.c
$(HACK_BIN)/xlockmore.o:	$(HACK_SRC)/xlockmore.c
$(HACK_BIN)/fps.o:		$(HACK_SRC)/fps.c

$(UTILDIR_OBJS):
	cd $(UTILS_BIN) ; $(MAKE) $(@F) CC="$(CC)" CFLAGS="$(CFLAGS)"
$(JWXYZ_OBJS):
	cd $(JWXYZ_BIN) ; $(MAKE) $(@F) CC="$(CC)" CFLAGS="$(CFLAGS)"
$(HACKDIR_OBJS):
	cd $(HACK_BIN)  ; $(MAKE) $(@F) CC="$(CC)" CFLAGS="$(CFLAGS)"


# How we build object files in this directory.
HACK_CFLAGS_BASE=$(INCLUDES) $(DEFS) $(CPPFLAGS) $(CFLAGS) $(X_CFLAGS)
.c.o:
	$(CC) -c $(HACK_CFLAGS_BASE) $<

# Make sure the images have been packaged. This is the first one hit.
#
../images/gen/wood_png.h:
	cd ../images && $(MAKE)
	@if ! [ -f "$@" ]; then \
	  echo; echo $@ "wasn't built -- try 'gmake' instead?"; echo; exit 1; \
	fi

# How to build the "xscreensaver-gl-visual" program, that lets the daemon
# know which visual is the right one for GL programs.
#
GLH1=xscreensaver-gl-visual.o $(UTILS_BIN)/visual-gl.o
GLH2=$(UTILS_BIN)/visual.o $(UTILS_BIN)/resources.o
xscreensaver-gl-visual:        $(GLH1) $(GLH2)
	$(CC) $(LDFLAGS) -o $@ $(GLH1) $(GLH2) $(LIBS) $(X_LIBS) $(HACK_POST2)


# These hacks use a slightly-differently-compiled variant of recanim.c.
# This is how to make the the other .o file from it.
#
XLM_CFLAGS=-DUSE_GL $(INCLUDES) $(DEFS) $(CPPFLAGS) $(CFLAGS) $(X_CFLAGS)
recanim-gl.o: $(HACK_SRC)/recanim.c
	$(CC) -o $@ -c $(XLM_CFLAGS) $(HACK_SRC)/recanim.c

CC_HACK		= $(CC) $(LDFLAGS)

THREAD_OBJS	     = $(UTILS_BIN)/thread_util.o
TRACK_OBJS	     = rotator.o trackball.o gltrackball.o
HACK_TRACK_OBJS	     = $(HACK_OBJS) $(TRACK_OBJS)
HACK_GRAB_OBJS	     = $(HACK_OBJS) $(GRAB_OBJS)
HACK_TRACK_GRAB_OBJS = $(HACK_TRACK_OBJS) $(GRAB_OBJS)
TEXT		     = $(UTILS_BIN)/textclient.o

ATLANTIS_OBJS = $(HACK_OBJS) dolphin.o shark.o swim.o whale.o $(PNG)
atlantis:	atlantis.o	$(ATLANTIS_OBJS)
	$(CC_HACK) -o $@ $@.o	$(ATLANTIS_OBJS) $(PNG_LIBS)

ATUNNEL_OBJS = $(HACK_OBJS) tunnel_draw.o $(PNG)
atunnel:	atunnel.o	$(ATUNNEL_OBJS)
	$(CC_HACK) -o $@ $@.o   $(ATUNNEL_OBJS) $(PNG_LIBS)

cage:		cage.o		$(PNG) $(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PNG) $(HACK_OBJS) $(PNG_LIBS)

FLURRY_OBJS_1 = flurry-smoke.o flurry-spark.o flurry-star.o flurry-texture.o
FLURRY_OBJS = $(FLURRY_OBJS_1) $(HACK_OBJS)

flurry:		flurry.o	$(FLURRY_OBJS)
	$(CC_HACK) -o $@ $@.o	$(FLURRY_OBJS) $(HACK_LIBS) -lm

GEARS_OBJS_1=normals.o involute.o
GEARS_OBJS=$(GEARS_OBJS_1) $(HACK_TRACK_OBJS)
gears:		gears.o		tube.o $(GEARS_OBJS)
	$(CC_HACK) -o $@ $@.o	tube.o $(GEARS_OBJS) $(HACK_LIBS)

MOEBIUS_OBJS=sphere.o tube.o $(PNG) $(HACK_TRACK_OBJS)
moebius:	moebius.o	$(MOEBIUS_OBJS)
	$(CC_HACK) -o $@ $@.o	$(MOEBIUS_OBJS) $(HACK_LIBS) $(PNG_LIBS)

PIPE_OBJS=pipeobjs.o buildlwo.o sphere.o teapot.o normals.o
pipes:		pipes.o		$(PIPE_OBJS) $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PIPE_OBJS) $(HACK_TRACK_OBJS) $(HACK_LIBS)

superquadrics:	superquadrics.o	$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_OBJS) $(HACK_LIBS)

morph3d:	morph3d.o	$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_OBJS) $(HACK_LIBS)

rubik:		rubik.o		$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

STAIRS=sphere.o $(PNG) $(HACK_TRACK_OBJS)
stairs:		stairs.o	$(STAIRS)
	$(CC_HACK) -o $@ $@.o	$(STAIRS) $(HACK_LIBS) $(PNG_LIBS)

SPROING1=$(HACK_OBJS) sproingiewrap.o gllist.o
SPROING2=s1_1.o s1_2.o s1_3.o s1_4.o s1_5.o s1_6.o s1_b.o
sproingies: sproingies.o	$(SPROING1) $(SPROING2)
	$(CC_HACK) -o $@ $@.o	$(SPROING1) $(SPROING2) $(HACK_LIBS)

LAMENTOBJS = gllist.o lament_model.o $(HACK_TRACK_OBJS) $(PNG) normals.o
lament:		lament.o	$(LAMENTOBJS)
	$(CC_HACK) -o $@ $@.o	$(LAMENTOBJS) $(PNG_LIBS)

lament_dxf::
	./dxf2gl.pl --smooth --layers lament.dxf lament_model.c


B3D_OBJS = b_sphere.o b_draw.o b_lockglue.o $(HACK_OBJS)
bubble3d:	bubble3d.o	$(B3D_OBJS)
	$(CC_HACK) -o $@ $@.o	$(B3D_OBJS) $(HACK_LIBS)

PLANET_OBJS=sphere.o $(PNG) $(HACK_TRACK_OBJS)
glplanet:	glplanet.o	$(PLANET_OBJS)
	$(CC_HACK) -o $@ $@.o   $(PLANET_OBJS) $(PNG_LIBS)

DYMAXIOBJS=dymaxionmap-coords.o normals.o $(PLANET_OBJS)
dymaxionmap:	dymaxionmap.o	$(DYMAXIOBJS)
	$(CC_HACK) -o $@ $@.o   $(DYMAXIOBJS) $(PNG_LIBS)

pulsar:		pulsar.o	$(HACK_OBJS) $(PNG)
	$(CC_HACK) -o $@ $@.o   $(HACK_OBJS) $(PNG) $(PNG_LIBS)

EXTR1=extrusion.o extrusion-helix2.o extrusion-helix3.o
EXTR2=extrusion-helix4.o extrusion-joinoffset.o extrusion-screw.o
EXTR3=extrusion-taper.o extrusion-twistoid.o $(PNG) $(HACK_TRACK_OBJS)
extrusion:			$(EXTR1) $(EXTR2) $(EXTR3)
	$(CC_HACK) -o $@	$(EXTR1) $(EXTR2) $(EXTR3) $(GLE_LIBS)

sierpinski3d:	sierpinski3d.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o   $(HACK_TRACK_OBJS) $(HACK_LIBS)

gflux:		gflux.o		$(HACK_TRACK_GRAB_OBJS)
	$(CC_HACK) -o $@ $@.o   $(HACK_TRACK_GRAB_OBJS) $(HACK_LIBS)

SW_OBJS=starwars.o glut_stroke.o glut_swidth.o $(TEXT) $(HACK_OBJS)
starwars:			$(SW_OBJS)
	$(CC_HACK) -o $@	$(SW_OBJS) $(HACK_LIBS) $(TEXT_LIBS)

GLT1=gltext.o glut_stroke.o glut_swidth.o tube.o sphere.o
GLT2=$(TEXT) $(HACK_TRACK_OBJS)
gltext:				$(GLT1) $(GLT2)
	$(CC_HACK) -o $@	$(GLT1) $(GLT2) $(HACK_LIBS) $(TEXT_LIBS)

DB_OBJS=sphere.o tube.o $(HACK_TRACK_OBJS)
dangerball:	dangerball.o	$(DB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(DB_OBJS) $(HACK_LIBS)

circuit:	circuit.o	$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o   $(HACK_OBJS) $(HACK_LIBS)

menger:		menger.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o   $(HACK_TRACK_OBJS) $(HACK_LIBS)

engine:		engine.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o   $(HACK_TRACK_OBJS) $(HACK_LIBS)

flipscreen3d:	flipscreen3d.o	$(HACK_TRACK_GRAB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_GRAB_OBJS) $(HACK_LIBS)

glsnake:	glsnake.o	$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_OBJS) $(HACK_LIBS)

boxed:		boxed.o		$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_OBJS) $(HACK_LIBS)

glforestfire:	glforestfire.o	$(PNG) $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PNG) $(HACK_TRACK_OBJS) $(PNG_LIBS)

sballs:		sballs.o	$(PNG) $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PNG) $(HACK_TRACK_OBJS) $(PNG_LIBS)

cubenetic:	cubenetic.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

spheremonics:	spheremonics.o	normals.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	normals.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

LL_OBJS=marching.o $(PNG) normals.o $(HACK_TRACK_OBJS)
lavalite:	lavalite.o	$(LL_OBJS)
	$(CC_HACK) -o $@ $@.o	$(LL_OBJS) $(PNG_LIBS)

queens:		queens.o	chessmodels.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o   chessmodels.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

endgame:	endgame.o	chessmodels.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o   chessmodels.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

glblur:	glblur.o		$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

TOAST1=toaster.o toaster_base.o toaster_handle.o toaster_handle2.o
TOAST2=toaster_jet.o toaster_knob.o toaster_slots.o toaster_wing.o
TOAST3=toast.o toast2.o flyingtoasters.o gllist.o $(PNG) $(HACK_TRACK_OBJS)
flyingtoasters:			$(TOAST1) $(TOAST2) $(TOAST3)
	$(CC_HACK) -o $@	$(TOAST1) $(TOAST2) $(TOAST3) $(PNG_LIBS)

toaster_dxf::
	@set -e ; \
	for f in \
	  toaster.dxf \
	  toaster_base.dxf \
	  toaster_handle.dxf \
	  toaster_handle2.dxf \
	  toaster_jet.dxf \
	  toaster_knob.dxf \
	  toaster_slots.dxf \
	  toaster_wing.dxf \
	  toast.dxf \
	  toast2.dxf \
	; do \
	  f2=`echo $$f | sed 's/dxf$$/c/'` ; \
	  ./dxf2gl.pl --normalize --smooth $$f $$f2 ; \
	done ; \

COW1=cow_face.o cow_hide.o cow_hoofs.o cow_horns.o cow_tail.o cow_udder.o
COW2=bouncingcow.o gllist.o $(PNG) $(HACK_TRACK_OBJS)
bouncingcow:			$(COW1) $(COW2)
	$(CC_HACK) -o $@	$(COW1) $(COW2) $(PNG_LIBS)

ROBO1=robot.o robot-wireframe.o gllist.o $(PNG) sphere.o
ROBO2=winduprobot.o $(GEARS_OBJS_1) $(TEXT) $(HACK_TRACK_OBJS)
winduprobot:			$(ROBO1) $(ROBO2)
	$(CC_HACK) -o $@	$(ROBO1) $(ROBO2) $(PNG_LIBS) $(TEXT_LIBS)

winduprobot_dxf::
	./dxf2gl.pl --smooth --layers robot.dxf robot.c
	./dxf2gl.pl --wireframe robot-wireframe.dxf robot-wireframe.c

CAM_OBJS=seccam.o gllist.o vigilance.o $(HACK_TRACK_OBJS)
vigilance:			$(CAM_OBJS)
	$(CC_HACK) -o $@	$(CAM_OBJS) $(HACK_LIBS)

seccam_dxf::
	./dxf2gl.pl --smooth --layers seccam.dxf seccam.c

glslideshow:	glslideshow.o	$(HACK_GRAB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_GRAB_OBJS) $(HACK_LIBS)

jigglypuff:	jigglypuff.o	$(PNG) $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PNG) $(HACK_TRACK_OBJS) $(PNG_LIBS)

klein:		klein.o		$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

surfaces:	surfaces.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

hypertorus:	hypertorus.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

projectiveplane: projectiveplane.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	   $(HACK_TRACK_OBJS) $(HACK_LIBS)

romanboy:	romanboy.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

etruscanvenus:	etruscanvenus.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

sphereeversion:	sphereeversion.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	 $(HACK_TRACK_OBJS) $(HACK_LIBS)

glmatrix:	glmatrix.o	$(PNG) $(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PNG) $(HACK_OBJS) $(PNG_LIBS)

cubestorm:	cubestorm.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

glknots:	glknots.o	tube.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	tube.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

blocktube:	blocktube.o	$(PNG) $(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PNG) $(HACK_OBJS) $(PNG_LIBS)

flipflop:	flipflop.o	$(HACK_TRACK_GRAB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_GRAB_OBJS) $(HACK_LIBS)

antspotlight:	antspotlight.o	sphere.o $(HACK_TRACK_GRAB_OBJS)
	$(CC_HACK) -o $@ $@.o	sphere.o $(HACK_TRACK_GRAB_OBJS) $(HACK_LIBS)

polytopes:	polytopes.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

STONER_OBJS=stonerview-move.o stonerview-osc.o stonerview-view.o
stonerview:	stonerview.o	$(STONER_OBJS) $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(STONER_OBJS) $(HACK_TRACK_OBJS) $(HACK_LIBS)

molecules.h:
	@echo "building molecules.h from $(HACK_SRC)/images/molecules/*.pdb"; \
	UTILS_SRC="$(UTILS_SRC)" \
	$(srcdir)/molecules.sh molecules.h $(HACK_SRC)/images/molecules/*.pdb

MOLECULE_OBJS=sphere.o tube.o $(HACK_TRACK_OBJS)
molecule.o:	molecules.h
molecule:	molecule.o	$(MOLECULE_OBJS)
	$(CC_HACK) -o $@ $@.o   $(MOLECULE_OBJS) $(HACK_LIBS)

gleidescope:	gleidescope.o	$(PNG) $(HACK_GRAB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PNG) $(HACK_GRAB_OBJS) $(PNG_LIBS)

mirrorblob:	mirrorblob.o	$(HACK_TRACK_GRAB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_GRAB_OBJS) $(PNG_LIBS)

blinkbox:	blinkbox.o	sphere.o $(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	sphere.o $(HACK_OBJS) $(HACK_LIBS)

noof:	noof.o			$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_OBJS) $(HACK_LIBS)

PH_OBJS=polyhedra-gl.o normals.o teapot.o $(HACK_TRACK_OBJS)
polyhedra:	polyhedra.o 	$(PH_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PH_OBJS) $(HACK_LIBS)

antinspect:	antinspect.o	sphere.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	sphere.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

providence:	providence.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

pinion:		pinion.o	$(GEARS_OBJS)
	$(CC_HACK) -o $@ $@.o	$(GEARS_OBJS) $(HACK_LIBS)

moebiusgears:	moebiusgears.o	$(GEARS_OBJS)
	$(CC_HACK) -o $@ $@.o	$(GEARS_OBJS) $(HACK_LIBS)

boing:		boing.o		normals.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	normals.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

carousel:	carousel.o	$(HACK_TRACK_GRAB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_GRAB_OBJS) $(HACK_LIBS)

fliptext:	fliptext.o	$(TEXT) $(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(TEXT) $(HACK_OBJS) $(HACK_LIBS) $(TEXT_LIBS)

antmaze:	antmaze.o	sphere.o tube.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	sphere.o tube.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

TANGRAM_OBJS=tangram_shapes.o $(HACK_OBJS)
tangram:	tangram.o	$(TANGRAM_OBJS)
	$(CC_HACK) -o $@ $@.o	$(TANGRAM_OBJS) $(HACK_LIBS)

crackberg:	crackberg.o	$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_OBJS) $(HACK_LIBS)

glhanoi:	glhanoi.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

cube21:		cube21.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

TIMETUNNEL_OBJS = $(PNG)  $(HACK_TRACK_OBJS)
timetunnel:	timetunnel.o	$(TIMETUNNEL_OBJS)
	$(CC_HACK) -o $@ $@.o   $(TIMETUNNEL_OBJS) $(PNG_LIBS)

JUGG_OBJS=sphere.o tube.o $(HACK_TRACK_OBJS)
juggler3d:	juggler3d.o	$(JUGG_OBJS)
	$(CC_HACK) -o $@ $@.o	$(JUGG_OBJS) $(HACK_LIBS)

dnalogo:	dnalogo.o      tube.o sphere.o normals.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o  tube.o sphere.o normals.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

topblock:	topblock.o	sphere.o tube.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	sphere.o tube.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

SCHOOL_OBJS=glschool.o glschool_alg.o glschool_gl.o sphere.o tube.o normals.o
glschool:			$(SCHOOL_OBJS) $(HACK_OBJS)
	$(CC_HACK) -o $@	$(SCHOOL_OBJS) $(HACK_OBJS) $(HACK_LIBS)

glcells:	glcells.o	$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_OBJS) $(HACK_LIBS)

voronoi:	voronoi.o	$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_OBJS) $(HACK_LIBS)

lockward:	lockward.o	$(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_OBJS) $(HACK_LIBS)

cubicgrid:	cubicgrid.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

hypnowheel:	hypnowheel.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

TENTACLE_OBJS=normals.o $(PNG) $(HACK_TRACK_OBJS)
skytentacles:	skytentacles.o	$(TENTACLE_OBJS)
	$(CC_HACK) -o $@ $@.o	$(TENTACLE_OBJS) $(PNG_LIBS)

SONAR_OBJS = sonar-sim.o sonar-icmp.o $(UTILS_BIN)/async_netdb.o \
	     $(THREAD_OBJS) $(UTILS_BIN)/aligned_malloc.o \
	     $(HACK_TRACK_OBJS)
sonar-icmp.o: sonar-icmp.c
	$(CC) -c $(HACK_CFLAGS_BASE) $(THREAD_CFLAGS) $<
sonar:		sonar.o		$(SONAR_OBJS)
	$(CC_HACK) -o $@ $@.o	$(THREAD_CFLAGS) $(SONAR_OBJS) $(LIBCAP_LIBS) $(THREAD_LIBS) $(HACK_LIBS)

JIGSAW_OBJS=normals.o $(UTILS_BIN)/spline.o $(HACK_TRACK_GRAB_OBJS)
jigsaw:		jigsaw.o	$(JIGSAW_OBJS)
	$(CC_HACK) -o $@ $@.o	$(JIGSAW_OBJS) $(HACK_LIBS)

PHOTOPILE_OBJS=dropshadow.o  $(HACK_GRAB_OBJS)
photopile:	photopile.o	$(PHOTOPILE_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PHOTOPILE_OBJS) $(HACK_LIBS)

rubikblocks:	rubikblocks.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

HILB_OBJS=sphere.o tube.o $(HACK_TRACK_OBJS)
hilbert:	hilbert.o	$(HILB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HILB_OBJS) $(HACK_LIBS)

CCUBE1=companion.o companion_quad.o companion_disc.o companion_heart.o
CCUBE2=gllist.o $(HACK_TRACK_OBJS)
companioncube:			$(CCUBE1) $(CCUBE2)
	$(CC_HACK) -o $@	$(CCUBE1) $(CCUBE2) $(HACK_LIBS)

TBIT1=tronbit.o tronbit_idle1.o tronbit_idle2.o tronbit_no.o tronbit_yes.o
TBIT2=gllist.o $(HACK_TRACK_OBJS)
tronbit:			$(TBIT1) $(TBIT2)
	$(CC_HACK) -o $@	$(TBIT1) $(TBIT2) $(HACK_LIBS)

KALEIDOCYCLE_OBJS=kaleidocycle.o normals.o $(HACK_TRACK_OBJS)
kaleidocycle:			$(KALEIDOCYCLE_OBJS)
	$(CC_HACK) -o $@	$(KALEIDOCYCLE_OBJS) $(HACK_LIBS)

quasicrystal:	quasicrystal.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

unknownpleasures: unknownpleasures.o	$(PNG) $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o $(PNG) $(HACK_TRACK_OBJS) $(HACK_LIBS) $(PNG_LIBS)

geodesic: geodesic.o		 normals.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	 normals.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

geodesicgears: geodesicgears.o	 $(GEARS_OBJS)
	$(CC_HACK) -o $@ $@.o	 $(GEARS_OBJS) $(HACK_LIBS)

cityflow:	cityflow.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

splitflap_dxf::
	./dxf2gl.pl --normalize --smooth --layers splitflap.dxf splitflap_obj.c

FLAP_OBJS=splitflap_obj.o gllist.o splitflap.o $(TEXT) $(HACK_TRACK_OBJS)
splitflap:			$(FLAP_OBJS)
	$(CC_HACK) -o $@	$(FLAP_OBJS) $(PNG_LIBS) $(TEXT_LIBS)

unicrud:	unicrud.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

ES_OBJS=$(PNG) $(HACK_TRACK_OBJS)
energystream:	energystream.o	$(ES_OBJS)
	$(CC_HACK) -o $@ $@.o	$(ES_OBJS) $(PNG_LIBS) $(HACK_LIBS)

raverhoop:	raverhoop.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

HSTAT_OBJS=sphere.o normals.o $(HACK_TRACK_OBJS)
hydrostat:	hydrostat.o	$(HSTAT_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HSTAT_OBJS) $(HACK_LIBS)

discoball:	discoball.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

cubetwist:	cubetwist.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

cubestack:	cubestack.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

splodesic:	splodesic.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

hexstrut:	hexstrut.o	 normals.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	 normals.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

esper:	esper.o			$(HACK_GRAB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_GRAB_OBJS) $(HACK_LIBS)

ships_dxf::
	./dxf2gl.pl --normalize --layers ships.dxf ships.c

DAZ_OBJS=ships.o gllist.o $(HACK_TRACK_OBJS)
razzledazzle:	razzledazzle.o	$(DAZ_OBJS)
	$(CC_HACK) -o $@ $@.o	$(DAZ_OBJS) $(HACK_LIBS)

peepers:	peepers.o	 normals.o $(PNG) $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	 normals.o $(PNG) $(PNG_LIBS) $(HACK_TRACK_OBJS) $(HACK_LIBS)

crumbler:	crumbler.o	quickhull.o $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	quickhull.o $(HACK_TRACK_OBJS) $(HACK_LIBS)

maze3d:	maze3d.o		 $(PNG) $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	 $(PNG) $(PNG_LIBS) $(HACK_TRACK_OBJS) $(HACK_LIBS)

HANDSY_OBJS=gllist.o handsy_model.o normals.o $(HACK_TRACK_OBJS)
handsy:	handsy.o		 $(HANDSY_OBJS)
	$(CC_HACK) -o $@ $@.o	 $(HANDSY_OBJS) $(HACK_LIBS)

handsy_dxf::
	./dxf2gl.pl --smooth 28 --layers handsy.dxf handsy_model.c

gravitywell:	gravitywell.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

deepstars:	deepstars.o	$(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(HACK_TRACK_OBJS) $(HACK_LIBS)

gibson:		gibson.o	$(PNG) $(HACK_TRACK_OBJS)
	$(CC_HACK) -o $@ $@.o	$(PNG) $(HACK_TRACK_OBJS) $(PNG_LIBS)

covid19:	covid19.o	$(DB_OBJS)
	$(CC_HACK) -o $@ $@.o	$(DB_OBJS) $(HACK_LIBS)

HEADROOM_OBJS=gllist.o headroom_model.o normals.o $(HACK_TRACK_OBJS)
headroom:	headroom.o	 $(HEADROOM_OBJS)
	$(CC_HACK) -o $@ $@.o	 $(HEADROOM_OBJS) $(HACK_LIBS)

headroom_dxf::
	./dxf2gl.pl --layers headroom.dxf headroom_model.c

beats:		beats.o		sphere.o $(HACK_OBJS)
	$(CC_HACK) -o $@ $@.o	sphere.o $(HACK_OBJS) $(HACK_LIBS)

##############################################################################
#
# DO NOT DELETE: updated by make distdepend

