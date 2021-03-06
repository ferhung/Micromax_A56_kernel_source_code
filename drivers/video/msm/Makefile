obj-y := msm_fb.o

obj-$(CONFIG_FB_MSM_LOGO) += logo.o
obj-$(CONFIG_FB_BACKLIGHT) += msm_fb_bl.o

# MDP
obj-y += mdp.o
obj-y += mipi_backlight.o
obj-$(CONFIG_DEBUG_FS) += mdp_debugfs.o

ifeq ($(CONFIG_FB_MSM_MDP40),y)
obj-y += mdp4_util.o
else
obj-y += mdp_hw_init.o
obj-y += mdp_ppp.o
ifeq ($(CONFIG_FB_MSM_MDP31),y)
obj-y += mdp_ppp_v31.o
else
obj-y += mdp_ppp_v20.o
endif
endif

ifeq ($(CONFIG_FB_MSM_OVERLAY),y)
obj-y += mdp4_overlay.o
obj-y += mdp4_overlay_lcdc.o
ifeq ($(CONFIG_FB_MSM_MIPI_DSI),y)
obj-y += mdp4_overlay_dsi_video.o
obj-y += mdp4_overlay_dsi_cmd.o
else
obj-y += mdp4_overlay_mddi.o
endif
else
obj-y += mdp_dma_lcdc.o
endif

obj-$(CONFIG_FB_MSM_MDP303) += mdp_dma_dsi_video.o

ifeq ($(CONFIG_FB_MSM_DTV),y)
obj-y += mdp4_dtv.o
obj-y += mdp4_overlay_dtv.o
endif

obj-y += mdp_dma.o
obj-y += mdp_dma_s.o
obj-y += mdp_vsync.o
obj-y += mdp_cursor.o
obj-y += mdp_dma_tv.o
obj-$(CONFIG_ARCH_MSM7X27A) += msm_dss_io_7x27a.o
obj-$(CONFIG_ARCH_MSM8X60) += msm_dss_io_8x60.o
obj-$(CONFIG_ARCH_MSM8960) += msm_dss_io_8960.o

# EBI2
obj-$(CONFIG_FB_MSM_EBI2) += ebi2_lcd.o

# LCDC
obj-$(CONFIG_FB_MSM_LCDC) += lcdc.o

# MDDI
msm_mddi-objs := mddi.o mddihost.o mddihosti.o
obj-$(CONFIG_FB_MSM_MDDI) += msm_mddi.o

# External MDDI
msm_mddi_ext-objs := mddihost_e.o mddi_ext.o
obj-$(CONFIG_FB_MSM_EXTMDDI) += msm_mddi_ext.o

# MIPI gereric
msm_mipi-objs := mipi_dsi.o mipi_dsi_host.o
obj-$(CONFIG_FB_MSM_MIPI_DSI) += msm_mipi.o

# boot splash
obj-y += late_display.o

# MIPI manufacture
obj-$(CONFIG_FB_MSM_MIPI_DSI_TOSHIBA) += mipi_toshiba.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_NOVATEK) += mipi_novatek.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_RENESAS) += mipi_renesas.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_TRULY) += mipi_truly.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_OTM8009A_BOE) += mipi_otm8009a_boe.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_HX8369A_TCL) += mipi_hx8369a_tcl.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_HX8357C_HSD) += mipi_hx8357c_hsd.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_HX8357C_HSD_TRULY375) += mipi_hx8357c_hsd_truly375.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_HX8357C_APEX375) += mipi_hx8357c_apex375.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_ILI9486_HSD) += mipi_ili9486_hsd.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_ILI9486_HSD_DJN375) += mipi_ili9486_hsd_djn375.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_ILI9486_CPT_LEAD) += mipi_ili9486_cpt_lead.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_HX8357C_CPT) += mipi_hx8357c_cpt.o
obj-$(CONFIG_FB_MSM_MIPI_DSI_SIMULATOR) += mipi_simulator.o

# TVEnc
obj-$(CONFIG_FB_MSM_TVOUT) += tvenc.o
ifeq ($(CONFIG_FB_MSM_OVERLAY),y)
obj-$(CONFIG_FB_MSM_TVOUT) += mdp4_overlay_atv.o
endif

# MSM FB Panel
obj-y += msm_fb_panel.o
obj-$(CONFIG_FB_MSM_EBI2_TMD_QVGA_EPSON_QCIF) += ebi2_tmd20.o
obj-$(CONFIG_FB_MSM_EBI2_TMD_QVGA_EPSON_QCIF) += ebi2_l2f.o

ifeq ($(CONFIG_FB_MSM_MDDI_AUTO_DETECT),y)
obj-y += mddi_prism.o
obj-y += mddi_toshiba.o
obj-y += mddi_toshiba_vga.o
obj-y += mddi_toshiba_wvga_pt.o
obj-y += mddi_toshiba_wvga.o
obj-y += mddi_sharp.o
obj-y += mddi_orise.o
obj-y += mddi_quickvx.o
else
obj-$(CONFIG_FB_MSM_MDDI_PRISM_WVGA) += mddi_prism.o
obj-$(CONFIG_FB_MSM_MDDI_TOSHIBA_COMMON) += mddi_toshiba.o
obj-$(CONFIG_FB_MSM_MDDI_TOSHIBA_COMMON_VGA) += mddi_toshiba_vga.o
obj-$(CONFIG_FB_MSM_MDDI_TOSHIBA_WVGA_PORTRAIT) += mddi_toshiba_wvga_pt.o
obj-$(CONFIG_FB_MSM_MDDI_TOSHIBA_WVGA) += mddi_toshiba_wvga.o
obj-$(CONFIG_FB_MSM_MDDI_SHARP_QVGA_128x128) += mddi_sharp.o
obj-$(CONFIG_FB_MSM_MDDI_ORISE) += mddi_orise.o
obj-$(CONFIG_FB_MSM_MDDI_QUICKVX) += mddi_quickvx.o
endif

ifeq ($(CONFIG_FB_MSM_MIPI_PANEL_DETECT),y)
obj-y += mipi_default_panel.o mipi_default_video_hvga_pt.o
obj-y += mipi_hx8357c_hsd_cmd_hvga_pt.o mipi_hx8357c_hsd_video_hvga_pt.o
obj-y += mipi_hx8357c_hsd_truly375_video_hvga_pt.o
obj-y += mipi_hx8357c_apex375_video_hvga_pt.o
obj-y += mipi_ili9486_hsd_cmd_hvga_pt.o mipi_ili9486_hsd_video_hvga_pt.o
obj-y += mipi_ili9486_hsd_djn375_cmd_hvga_pt.o mipi_ili9486_hsd_djn375_video_hvga_pt.o
obj-y += mipi_ili9486_cpt_lead_cmd_hvga_pt.o mipi_ili9486_cpt_lead_video_hvga_pt.o
obj-y += mipi_hx8357c_cpt_cmd_hvga_pt.o mipi_hx8357c_cpt_video_hvga_pt.o
obj-y += mipi_hx8369a_tcl_cmd_wvga_pt.o
obj-y += mipi_otm8009a_boe_cmd_wvga_pt.o
obj-y += mipi_otm8009a_boe_video_wvga_pt.o
else
obj-$(CONFIG_FB_MSM_MIPI_TOSHIBA_VIDEO_WVGA_PT) += mipi_toshiba_video_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_TOSHIBA_VIDEO_WSVGA_PT) += mipi_toshiba_video_wsvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_NOVATEK_VIDEO_QHD_PT) += mipi_novatek_video_qhd_pt.o
obj-$(CONFIG_FB_MSM_MIPI_NOVATEK_CMD_QHD_PT) += mipi_novatek_cmd_qhd_pt.o
obj-$(CONFIG_FB_MSM_MIPI_RENESAS_VIDEO_FWVGA_PT) += mipi_renesas_video_fwvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_RENESAS_CMD_FWVGA_PT) += mipi_renesas_cmd_fwvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_TRULY_VIDEO_WVGA_PT) += mipi_truly_video_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_CMD_OTM8009A_BOE_WVGA_PT) += mipi_otm8009a_boe_cmd_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_VIDEO_OTM8009A_BOE_WVGA_PT) += mipi_otm8009a_boe_video_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_CMD_HX8369A_TCL_WVGA_PT) += mipi_hx8369a_tcl_cmd_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_VIDEO_HX8357C_HSD_HVGA_PT) += mipi_hx8357c_hsd_video_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_VIDEO_HX8357C_HSD_TRULY375_HVGA_PT) += mipi_hx8357c_hsd_truly375_video_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_VIDEO_HX8357C_APEX375_HVGA_PT) += mipi_hx8357c_apex375_video_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_VIDEO_HX8357C_CPT_HVGA_PT) += mipi_hx8357c_cpt_video_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_CMD_HX8357C_HSD_HVGA_PT) += mipi_hx8357c_hsd_cmd_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_CMD_ILI9486_HSD_HVGA_PT) += mipi_ili9486_hsd_cmd_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_VIDEO_ILI9486_HSD_HVGA_PT) += mipi_ili9486_hsd_video_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_CMD_ILI9486_HSD_DJN375_HVGA_PT) += mipi_ili9486_hsd_djn375_cmd_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_VIDEO_ILI9486_HSD_DJN375_HVGA_PT) += mipi_ili9486_hsd_djn375_video_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_CMD_ILI9486_CPT_LEAD_HVGA_PT) += mipi_ili9486_cpt_lead_cmd_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_VIDEO_ILI9486_CPT_LEAD_HVGA_PT) += mipi_ili9486_cpt_lead_video_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_CMD_HX8357C_CPT_HVGA_PT) += mipi_hx8357c_cpt_cmd_hvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_TRULY_CMD_WVGA_PT) += mipi_truly_cmd_wvga_pt.o
obj-$(CONFIG_FB_MSM_MIPI_SIMULATOR_VIDEO) += mipi_simulator_video.o
endif

obj-$(CONFIG_FB_MSM_LCDC_PANEL) += lcdc_panel.o
obj-$(CONFIG_FB_MSM_LCDC_PRISM_WVGA) += lcdc_prism.o
obj-$(CONFIG_FB_MSM_LCDC_SAMSUNG_WSVGA) += lcdc_samsung_wsvga.o
obj-$(CONFIG_FB_MSM_LCDC_CHIMEI_WXGA) += lcdc_chimei_wxga.o
obj-$(CONFIG_FB_MSM_LCDC_EXTERNAL_WXGA) += lcdc_external.o
obj-$(CONFIG_FB_MSM_HDMI_SII_EXTERNAL_720P) += hdmi_sii9022.o
obj-$(CONFIG_FB_MSM_LCDC_GORDON_VGA) += lcdc_gordon.o
obj-$(CONFIG_FB_MSM_LCDC_WXGA) += lcdc_wxga.o
obj-$(CONFIG_FB_MSM_LCDC_TOSHIBA_WVGA_PT) += lcdc_toshiba_wvga_pt.o
obj-$(CONFIG_FB_MSM_LCDC_TOSHIBA_FWVGA_PT) += lcdc_toshiba_fwvga_pt.o
obj-$(CONFIG_FB_MSM_LCDC_SHARP_WVGA_PT) += lcdc_sharp_wvga_pt.o
obj-$(CONFIG_FB_MSM_LCDC_AUO_WVGA) += lcdc_auo_wvga.o
obj-$(CONFIG_FB_MSM_LCDC_SAMSUNG_OLED_PT) += lcdc_samsung_oled_pt.o
obj-$(CONFIG_FB_MSM_HDMI_ADV7520_PANEL) += adv7520.o
obj-$(CONFIG_FB_MSM_LCDC_ST15_WXGA) += lcdc_st15.o
obj-$(CONFIG_FB_MSM_LCDC_QRDC_WXGA) += lcdc_qrdc.o
obj-$(CONFIG_FB_MSM_HDMI_MSM_PANEL) += hdmi_msm.o
obj-$(CONFIG_FB_MSM_EXT_INTERFACE_COMMON) += external_common.o
obj-$(CONFIG_FB_MSM_LCDC_TRULY_HVGA_IPS3P2335) += lcdc_truly_ips3p2335.o
obj-$(CONFIG_FB_MSM_LCDC_QVGA_ILI9340N) += lcdc_ili9340n.o

obj-$(CONFIG_FB_MSM_TVOUT) += tvout_msm.o

obj-$(CONFIG_FB_MSM_EXTMDDI_SVGA) += mddi_ext_lcd.o

obj-$(CONFIG_MSM_VIDC_1080P) += vidc/
obj-$(CONFIG_MSM_VIDC_720P) += vidc/

clean:
	rm *.o .*cmd
