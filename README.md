# Quick Download Binary
```bash
if [ ! -f .env]; then
	echo "WEBHOOK_URL=http://localhost:7777" > .env
fi

version=$(curl https://api.github.com/repos/fepfitra/whatshook/tags | jq .[0].name -r)
name=whatshook_$version
if [ -f $name ]; then
		echo "$name already exists!"
		exit 0
fi
wget https://github.com/fepfitra/whatshook/releases/download/${version}/whatshook -O $name
chmod +x $name
```

# Quick Start
```bash
WEBHOOK_URL=http://yourhook.com ./whatshook_x.x.x
```
