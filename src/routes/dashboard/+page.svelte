<script>
  import HeroV1 from '$lib/components/ui/HeroV1.svelte';
  import Icon from '@iconify/svelte';
</script>

<!--
 
TODO: 
- bikin stats jadi reusable component next update.
- tambah example graph next update.

 -->

<div class="flex flex-col gap-3">
      <div class="stats shadow bg-base-200">
            <div class="stat border-l-4 border-accent">
                  <div class="stat-figure text-5xl">
                        <Icon icon="material-symbols:universal-currency-alt-rounded"/>
                  </div>
                  <div class="stat-title flex flex-row items-center gap-2">
                        <!-- <Icon icon="material-symbols:credit-card" class="text-xl"/> -->
                        Budget - Agustus 2026
                  </div>
                  <div class="stat-value">Rp 10.950.000</div>
                  <div class="stat-desc text-success">+0.6% Less spending this week.</div>
            </div>
      </div>

      <div class="stats shadow bg-base-200 min-w-full">
            <div class="stat">
                  <div class="stat-figure text-5xl">
                        <Icon icon="material-symbols:credit-card"/>
                  </div>
                  <div class="stat-title">Sisa Kebutuhan</div>
                  <div class="stat-value">Rp 4.700.000</div>
                  <div class="stat-desc"><b>Rp 85.000</b> telah terpakai bulan ini.</div>
            </div>
            <div class="stat">
                  <div class="stat-figure text-5xl">
                        <Icon icon="material-symbols:heart-smile-rounded"/>
                  </div>
                  <div class="stat-title">Sisa Keinginan</div>
                  <div class="stat-value">2.000.000</div>
                  <div class="stat-desc"><b>Rp 10.000</b> telah terpakai bulan ini.</div>
            </div>
            <div class="stat">
                  <div class="stat-figure text-5xl">
                        <Icon icon="material-symbols:mail-rounded"/>
                  </div>
                  <div class="stat-title">Total Tabungan</div>
                  <div class="stat-value">35.780.000</div>
                  <div class="stat-desc"><b>Rp 0</b> telah terpakai bulan ini.</div>
            </div>
      </div>

      <!-- Table -->
       <div class="overflow-x-auto min-h-80">
            <table class="table">
                  <thead>
                        <tr>
                              <th>#</th>
                              <th>Nama Item</th>
                              <th>Kategori</th>
                              <th>Jumlah</th>
                              <th>Biaya</th>
                        </tr>
                  </thead>
                  <tbody>
                        <tr>
                              <th>1</th>
                              <th>Nasi Padang Yum Yum</th>
                              <th><span class="badge badge-primary">Jajan</span></th>
                              <th>2</th>
                              <th>Rp 24.000.00</th>
                        </tr>
                        <tr>
                              <th>2</th>
                              <th>Printer</th>
                              <th><span class="badge badge-primary">Jajan</span></th>
                              <th>1</th>
                              <th>Rp 540.000.00</th>
                        </tr>
                        <tr>
                              <th>3</th>
                              <th>100 Robux</th>
                              <th><span class="badge badge-secondary">Kebutuhan</span></th>
                              <th>1</th>
                              <th>Rp 92.500.00</th>
                        </tr>
                        <tr>
                              <th>4</th>
                              <th>Freddy Fazbear</th>
                              <th><span class="badge badge-secondary">Kebutuhan</span></th>
                              <th>100</th>
                              <th>Rp 999.999.999</th>
                        </tr>
                  </tbody>
            </table>
       </div>
</div>

<!-- <HeroV1>
      <div class="max-w-l">
            <h1 class="mb-2 text-3xl font-bold">Dashboard</h1>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Suscipit omnis nobis soluta animi hic quam cumque, inventore similique mollitia voluptatibus itaque libero molestiae, vel pariatur iste dolores quod reprehenderit eum!</p>
      </div>
</HeroV1> -->

<!-- <div class="min-h-30 bg-base-200 p-5 justify-center">
<ul class="list">
      <li class="list-row">
            <div class="max-w-1/2 ml-5">
                  <h1 class="text-3xl mb-3 text-bold">Happy Home of Robloxia.</h1>
                  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.
                        Aliquam, molestias? Dolore, laboriosam optio? Commodi,
                        quam modi? Vel nisi similique omnis sunt animi officia 
                        ratione molestias delectus incidunt! Dolorum, dignissimos 
                        voluptatem?</p>
            </div>
      </li>
      <li class="list-row">
            <div class="max-w-1/2 ml-5">
                  <h1 class="text-3xl mb-3 text-bold">Happy Home of Robloxia.</h1>
                  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.
                        Aliquam, molestias? Dolore, laboriosam optio? Commodi,
                        quam modi? Vel nisi similique omnis sunt animi officia 
                        ratione molestias delectus incidunt! Dolorum, dignissimos 
                        voluptatem?</p>
            </div>
      </li>
</ul>
</div> -->