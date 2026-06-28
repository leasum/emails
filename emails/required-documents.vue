<script setup>
const year = new Date().getFullYear()
const logoUrl = 'https://leasum.com/emails/logo-dark.png'

const recipientName = '{{ recipientName }}'
// Triple braces: the list of documents may contain HTML (e.g. <ul><li>…</li></ul>).
const documents = '{{{ documents }}}'
</script>

<template>
  <Layout>
    <Head>
      <Font family="Inria Serif" :weights="[400, 700]" fallback="Georgia, 'Times New Roman', serif" />
      <Font family="Inter" :weights="[400, 500, 600, 700]" fallback="Arial, sans-serif" />
    </Head>

    <Preheader>We need a few documents to move your file forward.</Preheader>

    <Section class="bg-zinc-100 font-sans">
      <Container class="max-w-[600px] px-6 py-10">

        <Row>
          <Column class="text-center">
            <Img :src="logoUrl" width="144" alt="Leasum" class="mx-auto" />
          </Column>
        </Row>

        <Spacer class="h-8" />

        <Section class="overflow-hidden rounded-2xl border-t-4 border-[#FFE37B] bg-white shadow-[0_10px_30px_-8px_rgba(24,24,27,0.10),0_4px_10px_-4px_rgba(24,24,27,0.06)]">
          <Section class="px-10 py-12">
            <Heading
              level="1"
              class="m-0 font-serif text-[26px] font-bold leading-tight text-zinc-900"
            >
              A few documents are required
            </Heading>

            <Spacer class="h-6" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Dear {{ recipientName }},
            </Text>

            <Spacer class="h-4" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              To move your file forward, we still need the following from you:
            </Text>

            <Spacer class="h-6" />

            <Section class="rounded-xl bg-zinc-50 px-6 py-5">
              <Text class="m-0 text-base leading-7 text-zinc-900">
                {{ documents }}
              </Text>
            </Section>

            <Spacer class="h-8" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              You can upload them securely from your dashboard. Once we receive them, we'll
              continue processing your file right away.
            </Text>

            <Spacer class="h-8" />

            <Button
              href="https://app.leasum.com/documents/upload"
              class="rounded-full bg-[#FFE37B] px-7 py-3 text-sm font-semibold text-zinc-900 no-underline"
            >
              Upload my documents
            </Button>

            <Spacer class="h-10" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Warm regards,<br />
              The Leasum team
            </Text>
          </Section>
        </Section>

        <Spacer class="h-8" />

        <Section class="px-6 text-center">
          <Text class="m-0 text-sm font-medium leading-6 text-zinc-500">
            Your international setup, finally on a single platform.
          </Text>
          <Spacer class="h-3" />
          <Text class="m-0 text-xs leading-5 text-zinc-400">
            Copyright &copy; {{ year }} Leasum.com All Rights Reserved
          </Text>
        </Section>

      </Container>
    </Section>
  </Layout>
</template>
