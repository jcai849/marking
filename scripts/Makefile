SUBMISSIONSDIR := ../submissions
SUBMISSIONS := $(wildcard $(SUBMISSIONSDIR)/*.rmd)
BUILT := $(addsuffix .built,$(basename $(SUBMISSIONS)))
MARKED := $(addsuffix .marked,$(basename $(wildcard $(SUBMISSIONSDIR)/*.build*)))

.PHONY: build mark init

init:
	./setup-dirs
	./setup-subs

build: $(BUILT)

%.built: %.rmd
	./build $< 2

mark: $(MARKED)

%.marked: %.buildsuccess
	./mark-success $<

%.marked: %.buildfailure
	./mark-failure $<

print-% : ; @echo $* = $($*)
