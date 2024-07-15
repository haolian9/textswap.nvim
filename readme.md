to exchange text between two places handily

## design choices, features, limits
* work with utf-8 text
* work in visual mode `v` and `V`, but not `ctrl-V`
* work across buffers

## status
* just works
* feature complete to me

## prerequisites
* nvim 0.10.*
* haolian9/infra.nvim

## usage
my personal config
```
m.x("X", ":lua require'textexchange'()<cr>")
cmds.create("Exchange", function() require("textexchange")() end, { nargs = 0, range = true })
```

## credits
* the awesome [vim-exchange](https://github.com/tommcdo/vim-exchange) which i had been using til nvim 0.7
