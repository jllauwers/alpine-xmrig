# alpine-xmrig
[XMRig miner](https://github.com/xmrig/xmrig) in an Alpine Linux Docker image.

The goal of this project is to quickly enable you to mine Monero without the hassle of knowing how to install or secure your mining software. 

Using an [Alpine Linux](https://www.alpinelinux.org/) container you get a very lightweight image ~4MB and the benefit of Alpine Linux's security model.
I have also configured this image to run the miner as a dedicated  restricted user.

# How to use
```bash
# docker run --restart unless-stopped --read-only -m 50M jllauwers/contentera-xmrig -l xmr-default.log --donate-level=1 --max-cpu-usage 50 -o %POOL% -u %WALLET%
```

Please refer to [xmrig documentation](https://github.com/xmrig/xmrig) for complete options list. 

## Docker Arguments
`--restart unless-stopped`

If the miner crashes we want the docker service to restart it.

`--read-only`

This image does not need rw access.
If there are bug/exploits in the pool/software you are a little more protected.

`-m 50M`

Restricts memory usage to 50MB.

`--donate-level=1`

By default XMRig allocates 5% of the mining operations (time) to the project owner (xmrig). Here the donate level is set to 1% (the minimum). 

`--max-cpu-usage=50`

Maximum CPU usage

## XMRig Arguments
`--help`

All standard XMRig arguments are supported, using `--help` will list all of them.
```bash
# docker run bjllauwers/contentera-xmrig --help
```
