<template>
<footer>
    <div class="form-user-buy">
    <div id="fullname+phonenum+date+time">
                ชื่อผู้ทำการจอง: <input type="text" name="name" id="flname">
                เบอร์โทรศัพท์มือถือ: <input type="tel" name="p_num" id="phone_number">
                วันที่: <input type="date" name="date_local" id="date_local">
                เวลา: <input type="time" name="time_local" id="time_local">
            </div>
    </div>
    <div class="footer-content">
<a href="#" class="bottom-button" @click="confirmBooking">ยืนยันการจอง</a>
</div>
</footer>

</template>

<script setup>

function confirmBooking() {
    alert("ขอบคุณสำหรับการทำรายการ");
    window.location.reload();
}

</script>

<style>

</style>