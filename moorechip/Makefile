
# add-overlay defines the target with following naming convention:
# <base>-<board>-dtbs = base.dtb board.dtbo
#
# Combined dtb target is also generated using the fdt_overlay tool.
# dtb-y += <base>-<board>.dtb

add-overlays = $(foreach o,$1,$(foreach b,$2,$(eval $(basename $b)-$(basename $o)-dtbs = $b $o) $(basename $b)-$(basename $o).dtb))

SUN_BASE_DTB += ../qcom/sun.dtb ../qcom/sun-v2.dtb ../qcom/sun-tp.dtb ../qcom/sun-tp-v2.dtb
SUN_APQ_BASE_DTB += ../qcom/sunp.dtb ../qcom/sunp-v2.dtb ../qcom/sunp-tp.dtb ../qcom/sunp-tp-v2.dtb

SUN_BOARDS += \
	sunp-ayn-odin3-overlay.dtbo

sun-dtb-$(CONFIG_ARCH_SUN) += $(SUN_BOARDS) $(SUN_BASE_DTB) $(SUN_APQ_BASE_DTB)
sun-overlays-dtb-$(CONFIG_ARCH_SUN) += $(SUN_BOARDS) $(SUN_BASE_DTB) $(SUN_APQ_BASE_DTB)
dtb-y += $(sun-dtb-y)

always-y        := $(dtb-y)
subdir-y        := $(dts-dirs)
subdir-y        += audio ../qcom/bt ../qcom/data display ../qcom/dsp ../qcom/eSE ../qcom/eva fingerprint ../qcom/graphics ../qcom/mm ../qcom/mmrm ../qcom/synx ../qcom/video ../qcom/wlan
clean-files     := *.dtb *.dtbo
