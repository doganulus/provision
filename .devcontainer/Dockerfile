FROM python:slim

ARG USERNAME=dogan

# Add a container user
RUN groupadd work -g 1000 \
   && useradd -ms /bin/bash $USERNAME -g 1000 -u 1000 \
   && printf "$USERNAME:$USERNAME" | chpasswd \
   && printf "$USERNAME ALL= NOPASSWD: ALL\\n" >> /etc/sudoers

USER $USERNAME

ENV PATH "/home/$USERNAME/.local/bin:${PATH}"

RUN python -m pip install --user ansible
