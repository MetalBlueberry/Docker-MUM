FROM debian:stretch as build

RUN apt-get update && apt-get install -y \
  libpcre3-dev \
  build-essential \
  libpthread-stubs0-dev \
  git

WORKDIR /home/builder

RUN git clone https://github.com/stealth/grab

WORKDIR grab

RUN make

FROM debian:stretch-slim
COPY --from=build /home/builder/grab/grab /usr/local/bin

WORKDIR /home/grab

# run as default command, not really useful as you can't specify the parameters
# docker run -v $(pwd):/home/grab --rm -it src grab "hello \w+" file.txt
# CMD ["grab"] 

# docker run -v $(pwd):/home/grab --rm -it src "hello \w+" file.txt
ENTRYPOINT ["grab"] 
