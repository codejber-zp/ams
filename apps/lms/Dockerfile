FROM docker.io/node:lts-alpine AS environment-setup

RUN npm i -g pnpm nx && \
	apk add --no-cache \
	dumb-init

FROM environment-setup AS common

WORKDIR /usr/src/app
COPY *.json \
	*.yaml \
	*.ts \
	*.js \
	./
RUN pnpm i

FROM common AS development

WORKDIR /usr/src/app
COPY apps/lms ./apps/lms
COPY libs ./libs

CMD ["nx", "run", "lms:start"]

# Production image, copy all the files and run next
FROM environment-setup AS production

ENV NODE_ENV=production
ENV PORT=3000
WORKDIR /usr/src/app
COPY next.config.js ./
COPY public ./public
COPY .next/standalone/apps/lms ./
COPY .next/standalone/package.json ./
COPY .next/standalone/node_modules ./node_modules
COPY .next/static ./.next/static
# RUN npm i sharp
RUN chown -R node:node .
USER node
EXPOSE 3000
# COPY --chown=node:node ./tools/scripts/entrypoints/api.sh /usr/local/bin/docker-entrypoint.sh
# ENTRYPOINT [ "docker-entrypoint.sh" ]
# Next.js collects completely anonymous telemetry data about general usage.
# Learn more here: https://nextjs.org/telemetry
# Uncomment the following line in case you want to disable telemetry.
ENV NEXT_TELEMETRY_DISABLED=1
CMD ["dumb-init", "node", "server.js"]
