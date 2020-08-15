SUBMISSIONSDIR := ../submissions
SUBMISSIONS := $(wildcard $(SUBMISSIONSDIR)/*.[rR][mM][dD])
BUILT := $(addsuffix .Rmd.built,$(basename $(SUBMISSIONS)))
MARKED := $(addsuffix .Rmd.marked,$(basename $(basename $(wildcard $(SUBMISSIONSDIR)/*.Rmd.built))))

.PHONY: build mark

build: $(BUILT)

%.Rmd.built: %.[Rr][mM][dD]
	./build $<

mark: $(MARKED)

%.Rmd.marked: ../build-success/%.html
	./mark $<

%.Rmd.marked: ../build-failure/%.Rmd
	./mark $<

print-% : ; @echo $* = $($*)
