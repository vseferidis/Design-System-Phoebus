<style>
  .avatar-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 20px;
    padding: 20px;
    background-color: #000;
    border: 2px dashed #8a2be2;
  }
 
  .avatar-item {
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>

<!-- Components -->

<!-- AvatarIconFocusMedium -->
<script>
  export let size = 32;
  export let iconSrc = "https://dashboard.codeparrot.ai/api/assets/Z208rw16ERs_8IAR";
  export let alt = "User avatar";
  $: iconSize = size / 2;
</script>

<div class="avatar-container" style="width: {size}px; height: {size}px;" tabindex="0">
  <div class="circle-base"></div>
  <div class="hover-effect"></div>
  <img src={iconSrc} alt={alt} class="user-icon" style="width: {iconSize}px; height: {iconSize}px;" />
</div>

<style>
  .avatar-container {
    position: relative;
    border-radius: 50%;
    border: 2px solid #5bb98c;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    outline: none;
  }

  .circle-base {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url('https://dashboard.codeparrot.ai/api/assets/Z208uA16ERs_8IAb');
    background-size: cover;
    border-radius: 50%;
  }

  .hover-effect {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url('https://dashboard.codeparrot.ai/api/assets/Z208uQ16ERs_8IAc');
    background-size: cover;
    border-radius: 50%;
    opacity: 0;
    transition: opacity 0.2s ease-in-out;
  }

  .avatar-container:hover .hover-effect,
  .avatar-container:focus .hover-effect {
    opacity: 1;
  }

  .user-icon {
    position: relative;
    z-index: 1;
    object-fit: contain;
  }
</style>