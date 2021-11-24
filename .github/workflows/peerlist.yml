name: 'peerlist-demo'
on:
  workflow_dispatch:
    inputs:
      username:
        required: true
        description: 'Peerlist username'
      card_size:
        description: 'Card size (sm, md, lg) or any number'
        default: 'lg'
      theme_name:
        description: 'Theme name'
        default: 'default'
      text_color:
        description: 'Text color'
      title_color:
        description: 'Title color'
      bg_color:
        description: 'Background color'
      output_path:
        default: 'images/peerlist-profile.png'
        description: 'Output path to upload the image'
      branch:
        default: 'master'
        description: 'Branch which you want to upload the image, change it depending on your main branch'
jobs:
  peerlist-run:
    name: Generate peerlist overview
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: browser-actions/setup-chrome@latest
      - uses: 'anuraghazra/peerlist-profile-action@main'
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          username: ${{github.event.inputs.username}}
          theme_name: ${{github.event.inputs.theme_name}}
          card_size: ${{github.event.inputs.card_size}}
          title_color: ${{github.event.inputs.title_color}}
          text_color: ${{github.event.inputs.text_color}}
          bg_color: ${{github.event.inputs.bg_color}}
          branch: ${{github.event.inputs.branch}}
