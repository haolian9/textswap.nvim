to swap text between two places handily

https://github.com/user-attachments/assets/03343fe4-3649-4848-b1c6-388818ff32ec


## design choices, features, limits
* work with utf-8 text
* work in visual mode `v` and `V`, but not `ctrl-V`
* work across buffers
* it's an undefined-behavior when the two places overlap

## status
* just works
* feature complete to me

## prerequisites
* nvim 0.10.*
* haolian9/infra.nvim

## usage
my personal config
```
m.x("X", ":lua require'textswap'()<cr>")

do --:Swap
  local spell = cmds.Spell("Swap", function(args, ctx)
    local textswap = require("textswap")
    if ctx.range ~= 0 then return textswap() end
    textswap.cancel()
  end)
  spell:enable("range")
  cmds.cast(spell)
end
```

## credits
* the awesome [vim-exchange](https://github.com/tommcdo/vim-exchange) which i had been using til nvim 0.7
