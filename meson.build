project(
    'zmqproxy', 
    ['c'],
	version: run_command('git', 'describe', '--always', '--dirty=+').stdout().strip(),
    default_options: [
        'default_library=static',
        'warning_level=3'
    ]
)

zmq_dep = dependency(
	'libzmq',
	not_found_message: 'libzmq not found! Please install libzmq3-dev or the appropriate package for your system.'
)
csp_dep = dependency('csp', required: true, fallback: ['csp', 'csp_dep'])
deps = [
    csp_dep,
    zmq_dep
]
executable(
    'zmqproxy',
    [
        'src/zmqproxy.c'
    ],
    dependencies: deps,
    install: true
)
