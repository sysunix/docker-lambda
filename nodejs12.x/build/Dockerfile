FROM lambci/lambda-base-2:build

ENV PATH=/var/lang/bin:$PATH \
    LD_LIBRARY_PATH=/var/lang/lib:$LD_LIBRARY_PATH \
    AWS_EXECUTION_ENV=AWS_Lambda_nodejs12.x \
    NODE_PATH=/opt/nodejs/node12/node_modules:/opt/nodejs/node_modules:/var/runtime/node_modules

RUN rm -rf /var/runtime /var/lang /var/rapid && \
  curl https://lambci.s3.amazonaws.com/fs/nodejs12.x.tgz | tar -zx -C /

# Add these as a separate layer as they get updated frequently
RUN pip install -U awscli boto3 aws-sam-cli==0.48.0 aws-lambda-builders==0.8.0 --no-cache-dir
