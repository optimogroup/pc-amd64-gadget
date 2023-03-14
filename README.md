## 1. Update model.json timestamp
Get the date using `date -Iseconds --utc`.

## 2. Sign the model.json file
`cat model.json | snap sign -k pc-model > model.model`

You might need to run `export GPG_TTY=$(tty)` first. 

## 3. Build the image
`ubuntu-image snap model.model --snap /root/pc-amd64-gadget/pc-pcds_22-0.3_amd64.snap`

## 4. Compress the image
`xz pc.img`
