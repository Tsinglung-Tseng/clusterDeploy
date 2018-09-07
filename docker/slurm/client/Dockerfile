FROM 192.168.1.133:5000/nis-client
RUN apt-get update && apt-get -y install slurm-llnl openssh-server 
ADD munge.key /etc/munge/munge.key
RUN chown munge:munge /etc/munge/munge.key
RUN chmod go-rw /etc/munge/munge.key
ADD startup.sh /etc/profile.d/
RUN chmod +x /etc/profile.d/startup.sh
#RUN /etc/init.d/munge restart
#CMD ["/etc/init.d/munge", "restart","daemon off;"]
CMD /etc/init.d/munge restart && bash
