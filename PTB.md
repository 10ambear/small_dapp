These vars won't work as it, you'll need to add your own. 

## Set up vars
export FORGE_ID=0xf40cc1a5ccca85dcb2b94a97496b3c31e6ff02f0df0627f4b7478ce202b9f92c \
export TO_ADDRESS=0x48ccc6e7c34bacfc8bb786b2ebd5e43b5b65011a48c0137e71cc794dc9f9e1f1 \
export PACKAGE_ID=0xf61948e03f1525db46ceff33601775d91d0fa9705e39c51d05afda2d6b806f58

## Can use this to make new swords
sui client ptb \
        --assign forge @$FORGE_ID \
        --assign to_address @$TO_ADDRESS \
        --move-call $PACKAGE_ID::my_module::new_sword forge 3 3 \
        --assign sword \
        --transfer-objects "[sword]" to_address \
        --gas-budget 20000000
