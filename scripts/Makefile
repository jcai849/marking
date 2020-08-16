SUBMISSIONSDIR := ../submissions
SUBMISSIONS := $(wildcard $(SUBMISSIONSDIR)/*.[rR][mM][dD])
BUILT := $(addsuffix .built,$(basename $(SUBMISSIONS)))
MARKED := $(addsuffix .marked,$(basename $(wildcard $(SUBMISSIONSDIR)/*.build*)))

.PHONY: build mark

build: $(BUILT)

%.built: %.[Rr][mM][dD]
	./build $< 2

mark: $(MARKED)

%.marked: %.buildsuccess
	./mark $<

%.marked: %.buildfailure
	./mark -bf $<

print-% : ; @echo $* = $($*)
