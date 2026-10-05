# Regenerate the printable STLs from the OpenSCAD source.
# Needs OpenSCAD 2025+ (manifold backend).

PARTS   := tray_left tray_right bezel_left bezel_right
STLS    := $(addprefix stl/,$(addsuffix .stl,$(PARTS)))
OPENSCAD ?= openscad

all: $(STLS)

stl/%.stl: c128d_case.scad
	@mkdir -p stl
	$(OPENSCAD) --backend=manifold --export-format=binstl -o $@ -D 'part="$*"' $<

preview.png: c128d_case.scad
	$(OPENSCAD) --render --backend=manifold --autocenter --viewall --projection=p \
	  --imgsize=2000,900 --camera=0,0,0,60,0,15,0 -o $@ $<

clean:
	rm -f $(STLS) preview.png

.PHONY: all clean
