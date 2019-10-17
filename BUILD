load("@stb//:stb.bzl", "stb_library")

stb_library(
    "stb",
    emit_definition_macro = "STB_DEFINE",
    stb_prefix = False,
    copts = [
        "-Wno-sign-compare",
        "-Wno-unused-value",
        "-Wno-unused-but-set-variable",
        "-Wno-format-overflow",
    ]
)

stb_library(
    "c_lexer",
    emit_definition_macro = "STB_C_LEXER_DEFINITION"
)

stb_library(
    "connected_components",
    emit_definition_macro = "STB_CONNECTED_COMPONENTS_DEFINITION"
)

stb_library(
   "divide",
    emit_definition_macro = "STB_DIVIDE_DEFINITION"
)

stb_library(
   "ds",
    emit_definition_macro = "STB_DS_DEFINITION"
)

stb_library(
   "dxt",
    emit_definition_macro = "STB_DXT_DEFINITION"
)

stb_library(
   "easy_font",
    emit_definition_macro = "STB_EASY_FONT_DEFINITION",
    copts = ["-Wno-unused-function"]
)

stb_library(
   "herringbone_wang_tile",
    emit_definition_macro = "STB_HERRINGBONE_WANG_TILE_DEFINITION"
)

stb_library(
    "image",
    emit_definition_macro = "STB_IMAGE_DEFINITION"
)

stb_library(
    "image_resize",
    emit_definition_macro = "STB_IMAGE_RESIZE_DEFINITION"
)

stb_library(
    "image_write",
    emit_definition_macro = "STB_IMAGE_WRITE_DEFINITION"
)

stb_library(
    "include",
    emit_definition_macro = "STB_INCLUDE_DEFINITION"
)

stb_library(
    "leakcheck",
    emit_definition_macro = "STB_LEAKCHECK_DEFINITION"
)

stb_library(
    "perlin",
    emit_definition_macro = "STB_PERLIN_DEFINITION"
)

stb_library(
    "rect_pack",
    emit_definition_macro = "STB_RECT_PACK_DEFINITION"
)

stb_library(
    "sprintf",
    emit_definition_macro = "STB_SPRINTF_DEFINITION"
)

stb_library(
    "textedit",
    emit_definition_macro = "STB_TEXTEDIT_DEFINITION"
)

stb_library(
    "tilemap_editor",
    emit_definition_macro = "STB_TILEMAP_EDITOR_DEFINITION",
    copts = ["-Wno-comment"]
)

stb_library(
    "truetype",
    emit_definition_macro = "STB_TRUETYPE_DEFINITION"
)

stb_library(
    "voxel_render",
    emit_definition_macro = "STB_VOXEL_RENDER_DEFINITION"
)

stb_library(
    "stretchy_buffer",
    stb_prefix = False
)

# stb_vorbis has a reversed mechanism
genrule(
    name = "vorbis_definition",
    outs = ["stb_vorbis.cpp"],
    cmd  = 'echo "#include <stb/{0}>" > $(@D)/{1}'.format(
        "stb_vorbis.c", "stb_vorbis.cpp"
    ),
    visibility = ["//visibility:private"],
)
cc_library(
    name = "vorbis",
    hdrs = ["src/stb_vorbis.c"],
    strip_include_prefix = "src",
    include_prefix = "stb",
    srcs = ["stb_vorbis.cpp"],
    copts = ["-Wno-unused-value"],
    visibility = ["//visibility:public"],
)
