SUBMISSIONSDIR := ../submissions
SUBMISSIONS := $(wildcard $(SUBMISSIONSDIR)/*.[rR][mM][dD])
BUILT := $(addsuffix .built,$(basename $(SUBMISSIONS)))
MARKED := $(addsuffix .marked,$(basename $(basename $(wildcard $(SUBMISSIONSDIR)/*.build*))))

.PHONY: build mark

build: $(BUILT)

%.built: %.[Rr][mM][dD]
	./build $< 2

mark: $(MARKED)

%.Rmd.marked: ../build-success/%.html
	./mark $<

%.Rmd.marked: ../build-failure/%.Rmd
	./mark $<

print-% : ; @echo $* = $($*)
