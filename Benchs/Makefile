COMMON = Impl.hs Data.hs 
GHCMAKE = ghc --make

PUT_BENCHS = bench_put_pstr.html bench_put_bs.html bench_put_word.html bench_put_words.html
GET_BENCHS = bench_get.html bench_get_big.html

.PHONY: all all_get all_put
all: $(PUT_BENCHS) $(GET_BENCHS)

all_get: $(GET_BENCHS)

all_put: $(PUT_BENCHS)

bench_get.html: Get
	./Get -o $@ pascalstr word

bench_get_big.html: Get
	./Get -o $@ big

bench_put_pstr.html: Put
	./Put -o $@ pstr

bench_put_bs.html: Put
	./Put -o $@ bs

bench_put_word.html: Put
	./Put -o $@ "words x"

bench_put_words.html: Put
	./Put -o $@ "words4 x"

Put: Put.hs $(COMMON)
	$(GHCMAKE) -O2 $@

Get: Get.hs $(COMMON)
	$(GHCMAKE) -O2 $@

.PHONY: clean
clean:
	-rm -f *.html Get Put *.o *.hi
