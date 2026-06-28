<script setup>
const year = new Date().getFullYear()
const logoUrl = 'https://leasum.com/emails/logo-dark.png'

const recipientName = '{{ recipientName }}'
const serviceName = '{{ serviceName }}'
const amount = '{{ amount }}'
const paymentUrl = '{{ paymentUrl }}'
</script>

<template>
  <Layout>
    <Head>
      <Font family="Inria Serif" :weights="[400, 700]" fallback="Georgia, 'Times New Roman', serif" />
      <Font family="Inter" :weights="[400, 500, 600, 700]" fallback="Arial, sans-serif" />
      <meta name="color-scheme" content="light only" />
      <meta name="supported-color-schemes" content="light only" />
      <Raw>
        <style>:root { color-scheme: light only; supported-color-schemes: light only; }</style>
      </Raw>
    </Head>

    <Preheader>One step left to start your {{ serviceName }}.</Preheader>

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
              One step left to get started
            </Heading>

            <Spacer class="h-6" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Dear {{ recipientName }},
            </Text>

            <Spacer class="h-4" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Thanks for starting your {{ serviceName }} with us. To kick things off, all
              that's left is to settle the payment below and we'll get straight to work.
            </Text>

            <Spacer class="h-6" />

            <Section class="rounded-xl bg-zinc-50 px-6 py-5 text-center">
              <Text class="m-0 text-sm leading-6 text-zinc-500">Amount due</Text>
              <Text class="m-0 font-sans text-[32px] font-bold leading-tight text-zinc-900">
                {{ amount }}
              </Text>
              <Text class="m-0 text-sm leading-6 text-zinc-500">{{ serviceName }}</Text>
            </Section>

            <Spacer class="h-8" />

            <Button
              :href="paymentUrl"
              class="rounded-full bg-[#FFE37B] px-7 py-3 text-sm font-semibold text-zinc-900 no-underline"
            >
              Pay {{ amount }}
            </Button>

            <Spacer class="h-10" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Any questions? Just reply to this email or reach us from your dashboard. We're
              happy to help.
            </Text>

            <Spacer class="h-8" />

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
