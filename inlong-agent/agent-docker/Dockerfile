#
# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.
#
FROM openjdk:8-jdk-alpine
# add tarball from target output
ARG AGENT_TARBALL
ADD ${AGENT_TARBALL} /opt/inlong-agent
EXPOSE 8008
ENV MANAGER_OPENAPI_IP=127.0.0.1
ENV MANAGER_OPENAPI_PORT=8082
ENV DATAPROXY_IP=127.0.0.1
ENV DATAPROXY_PORT=46801
ENV ETH_NETWORK=eth0
WORKDIR /opt/inlong-agent
ADD agent-docker.sh bin/
RUN chmod +x bin/agent-docker.sh
CMD ["bin/agent-docker.sh"]
