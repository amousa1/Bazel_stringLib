load("//:def.bzl", "string_build_setting")

string_build_setting(
    name = "stringJob",
    build_setting_default = "Engineer"
)


cc_library(
	name = "string",
	srcs = select({
		":actor-name" : ["src/string-actor.c"],
		":hero-name"  : ["src/string-hero.c"],
		"//conditions:default" :["src/string.c"],
		}),
	hdrs = ["inc/string.h"],
)

config_setting(
	name = "actor-name",
	flag_values  = { ":stringJob" : "actor" },
)

config_setting(
	name = "hero-name",
	flag_values  = { ":stringJob" : "hero" },
)












#######################################################################################################################
# ## The below code is commented as platform usage requires additional configuraiton to point to c++ toolchain.
# ##constraint_setting(name = "job")
# ##constraint_value(name = "actor" , constraint_setting = "job")
# ##constraint_value(name = "hero" , constraint_setting = "job")
# ##
# ##
# ##constraint_setting(name = "movie")
# ##constraint_value(name = "piratesofcarrebian" , constraint_setting = "movie")
# ##constraint_value(name = "avengers" , constraint_setting = "movie")
# ##
# ##
# ##platform(
# ##	name = "actor-platform",
# ##	constraint_values = [ 
# ##		":actor", 
# ##		":piratesofcarrebian",
# ##		],
# ##)
# ##
# ##platform(
# ##	name = "hero-platform",
# ##	constraint_values = [ 
# ##		":hero",
# ##		":avengers",
# ##		],
# ##)