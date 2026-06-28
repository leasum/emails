<script setup>
// Mailgun fills these tokens at send time. We declare them as JS strings so Vue
// interpolates each one into the literal text "{{ token }}" in the built HTML —
// keeping Maizzle's components active (unlike v-pre, which would skip them too).
const preheader = '{{ preheader }}'
const heading = '{{ heading }}'
const recipientName = '{{ recipientName }}'
// Triple braces tell Mailgun not to HTML-escape the body (it may contain HTML).
const body = '{{{ body }}}'
const year = new Date().getFullYear()

// TODO: replace with the hosted logo URL once uploaded (see public/logo.png).
const logoUrl = 'https://leasum.com/email/logo.png'
</script>

<template>
  <Layout>
    <Head>
      <Font family="Inria Serif" :weights="[400, 700]" fallback="Georgia, 'Times New Roman', serif" />
      <Font family="Inter" :weights="[400, 500, 600, 700]" fallback="Arial, sans-serif" />
    </Head>

    <Preheader>{{ preheader }}</Preheader>

    <!-- Outer canvas -->
    <Section class="bg-zinc-100 font-sans">
      <Container class="max-w-[600px] px-6 py-10">

        <!-- Logo, centered -->
        <Row>
          <Column class="text-center">
            <Img :src="logoUrl" width="160" alt="Leasum" class="mx-auto" />
          </Column>
        </Row>

        <Spacer class="h-8" />

        <!-- Card -->
        <Section class="overflow-hidden rounded-2xl bg-white shadow-[0_10px_30px_-8px_rgba(24,24,27,0.10),0_4px_10px_-4px_rgba(24,24,27,0.06)]">
          <!-- Brand accent bar -->
          <Section class="h-1 bg-[#FFE37B] leading-none">&zwnj;</Section>

          <Section class="px-10 py-12">
            <Heading
              level="1"
              class="m-0 font-serif text-[26px] font-bold leading-tight text-zinc-900"
            >
              {{ heading }}
            </Heading>

            <Spacer class="h-6" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Hi {{ recipientName }},
            </Text>

            <Spacer class="h-4" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              {{ body }}
            </Text>

            <Spacer class="h-8" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Warm regards,<br />
              The Leasum team
            </Text>
          </Section>
        </Section>

        <Spacer class="h-8" />

        <!-- Footer -->
        <Section class="px-6 text-center">
          <Text class="m-0 text-sm font-medium leading-6 text-zinc-500">
            The operating system for your global sovereignty.
          </Text>
          <Spacer class="h-3" />
          <Text class="m-0 text-xs leading-5 text-zinc-400">
            Leasum &mdash; &copy; {{ year }}. All rights reserved.
            <br />
            Part of <Link href="https://xxi.business" class="text-zinc-500 underline">XXI, LLC</Link>
          </Text>
        </Section>

      </Container>
    </Section>
  </Layout>
</template>
