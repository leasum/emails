<script setup>
// Mailgun fills these tokens at send time. We declare them as JS strings so Vue
// interpolates each one into the literal text "{{ token }}" in the built HTML —
// keeping Maizzle's components active (unlike v-pre, which would skip them too).
const preheader = '{{ preheader }}'
const heading = '{{ heading }}'
const recipientName = '{{ recipientName }}'
// Triple braces tell Mailgun not to HTML-escape the body.
const body = '{{{ body }}}'
const year = new Date().getFullYear()
</script>

<template>
  <Layout class="bg-gray-50">
    <Preheader>{{ preheader }}</Preheader>

    <Container class="max-w-xl p-0 py-10 sm:p-6">
      <!-- Header -->
      <Section class="rounded-t-lg bg-gray-900 px-6 py-6">
        <Heading class="m-0 text-xl font-bold tracking-tight text-white">
          Leasum
        </Heading>
      </Section>

      <!-- Body -->
      <Section class="bg-white px-6 py-12">
        <Heading level="2" class="mb-6 text-2xl font-bold text-gray-950">
          {{ heading }}
        </Heading>

        <Text class="mb-6 text-base leading-6 text-gray-600">
          Hi {{ recipientName }},
        </Text>

        <Text class="mb-6 text-base leading-6 text-gray-600">
          {{ body }}
        </Text>
      </Section>

      <!-- Footer -->
      <Section class="rounded-b-lg bg-gray-50 px-6 py-9">
        <Text class="m-0 text-xs leading-5 text-gray-400">
          Leasum &mdash; &copy; {{ year }}. You're receiving this email because you have an account with Leasum.
        </Text>
      </Section>
    </Container>
  </Layout>
</template>
