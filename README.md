echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/queen-star24/test.git
git push -u origin main
sudo mkdir -p /mnt/tmp
sudo mount -t tmpfs -o size=4g tmpfs /mnt/tmp/
python3 bitcoin/build/test/functional/test_runner.py --cachedir=/mnt/tmp/cache --tmpdir=/mnt/tmp -r results.csv || echo "test_runner completed with non-zero exit code"

