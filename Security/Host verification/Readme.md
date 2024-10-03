# Running the verification script

git clone https://github.com/docker/docker-bench-security.git
cd docker-bench-security
./docker-bench-security.sh

dell@DESKTOP-E9H427N:~/docker-bench-security$ sudo ./docker-bench-security.sh
# --------------------------------------------------------------------------------------------
# Docker Bench for Security v1.6.0
#
# Docker, Inc. (c) 2015-2024
#
# Checks for dozens of common best-practices around deploying Docker containers in production.
# Based on the CIS Docker Benchmark 1.6.0.
# --------------------------------------------------------------------------------------------

Initializing 2024-10-03T18:13:50+02:00


Section A - Check results

[PASS] 5.21 - Ensure that the host's UTS namespace is not shared (Automated)
[PASS] 5.22 - Ensure the default seccomp profile is not Disabled (Automated)
[PASS] 7.3 - Ensure that all Docker swarm overlay networks are encrypted (Automated)

[INFO] Checks: 117
[INFO] Score: 4