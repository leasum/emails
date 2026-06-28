<script setup>
const year = new Date().getFullYear()
const logoUrl = 'https://i.imgur.com/nIYj26A.png'
</script>

<template>
  <Layout>
    <Head>
      <Font family="Inria Serif" :weights="[400, 700]" fallback="Georgia, 'Times New Roman', serif" />
      <Font family="Inter" :weights="[400, 500, 600, 700]" fallback="Arial, sans-serif" />
    </Head>

    <Preheader>Your LLC has been successfully formed.</Preheader>

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
              Your LLC is officially formed
            </Heading>

            <Spacer class="h-6" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Dear Clint,
            </Text>

            <Spacer class="h-4" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Congratulations — your company has been successfully registered. Your
              Limited Liability Company now legally exists and is ready to operate.
            </Text>

            <Spacer class="h-6" />

            <!-- Details panel -->
            <Section class="rounded-xl bg-zinc-50 px-6 py-5">
              <Text class="m-0 text-sm leading-6 text-zinc-500">Company name</Text>
              <Text class="m-0 text-base font-semibold leading-6 text-zinc-900">Northstar Ventures LLC</Text>
              <Spacer class="h-4" />
              <Text class="m-0 text-sm leading-6 text-zinc-500">State of formation</Text>
              <Text class="m-0 text-base font-semibold leading-6 text-zinc-900">Wyoming, United States</Text>
              <Spacer class="h-4" />
              <Text class="m-0 text-sm leading-6 text-zinc-500">Filing date</Text>
              <Text class="m-0 text-base font-semibold leading-6 text-zinc-900">June 28, 2026</Text>
            </Section>

            <Spacer class="h-8" />

            <Text class="m-0 text-base leading-7 text-zinc-600">
              Your formation documents — Articles of Organization and EIN confirmation —
              are available in your dashboard. We recommend keeping a copy for your records.
            </Text>

            <Spacer class="h-8" />

            <!-- CTA -->
            <Button
              href="https://app.leasum.com"
              class="rounded-full bg-[#FFE37B] px-7 py-3 text-sm font-semibold text-zinc-900 no-underline"
            >
              View my documents
            </Button>

            <Spacer class="h-10" />

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
