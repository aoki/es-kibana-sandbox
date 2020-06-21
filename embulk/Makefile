# Embulkのコンテナをビルド
build:
	docker build -t embulk .
.PHONY: build

# Seed からスキーマを作成
guess:
	docker run --net host --rm -v $(PWD):/work embulk guess -g ltsv seed.yml -o config.yml
.PHONY: guess

# Embulk preview
preview:
	docker run --net host --rm -v $(PWD):/work embulk preview -G config.yml
.PHONY: preview

# Embulk run
run:
	docker run --net host --rm -v $(PWD):/work embulk run config.yml -c diff.yml -r resume.yml
.PHONY: run

