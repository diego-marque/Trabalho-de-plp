<template>
  <el-container>
    <el-row class="footer">
      <div class="teste">
        <el-row>
          <div class="aviso_footer">
            Grécia Antiga
          </div>
        </el-row>
        <el-row>
          <div class="mensagem_footer">Design e desenvolvimento por Berto, Diego, Jean, Leo e Vitin</div>
        </el-row>
      </div>
    </el-row>
  </el-container>
</template>

<style>
.footer {
  background-color: #2cacb2;
  height: 100%;
  width: 100%;
  padding-right: 20px;
  display: flex;
  justify-content: flex-end;
}
.aviso_footer {
  font-weight: lighter;
  margin-top: 5px;
  color: #f0f0f0;
  font-size: 14px;
}

.teste {
  display: flex;
  justify-content: space-between;
  height: 55px;
  width: 98%;
  align-items: center;
}

.mensagem_footer {
  font-weight: lighter;
  margin-top: 5px;
  color: #f0f0f0;
  font-size: 14.5px;
}
@media screen and (max-width: 500px) {
  .footer {
    padding-right: 0px;
  }

  .aviso_footer {
    font-weight: lighter;
    margin-top: 5px;
    color: #f0f0f0;
    font-size: 10px;
  }
}
</style>

<script>
export default {
  name: "Footer",
  data() {
    return {};
  }
};
</script>
