
<?php
include 'DB.php';

class Total
{
  protected $totalHargaRawon;
  protected $totalHargaSoto;
  protected $totalHargaKare;
  protected $totalHargaTeh;
  protected $totalHargaJeruk;
  protected $totalHargaMarimas;

  protected $totalMakan;
  protected $totalMinum;

  protected $totalSeluruh;
  protected $coba;

  protected $detail;
  protected $produk;

}

class Produk {
private $hargaRawon;
private $hargaSoto;
private $hargaKare;
private $hargaTeh;
private $hargaJeruk;
private $hargaMarimas;



 function __construct() {
  $db = new DB();
        
  $users = $db->getRows('produk',array('order_by'=>'id_produk DESC'));

  foreach ($users as $row) {
    $harga[$row['nama']] = $row['harga'];
  }

  extract($harga);

  $this->hargaRawon = $Rawon;
  $this->hargaSoto = $Soto;
  $this->hargaKare = $Kare;
  $this->hargaTeh = $Teh;
  $this->hargaJeruk = $Jeruk;
  $this->hargaMarimas = $Marimas;
 }

  public function getHargaRawon()
 {
   return $this->hargaRawon;
 }
 public function getHargaSoto()
 {
   return $this->hargaSoto;
 }
 public function getHargaKare()
 {
   return $this->hargaKare;
 }
 public function getHargaTeh()
 {
   return $this->hargaTeh;
 }
 public function getHargaJeruk()
 {
   return $this->hargaJeruk;
 }
 public function getHargaMarimas()
 {
   return $this->hargaMarimas;
 }
}


class Detail {

private $JmlRawon;
private $JmlSoto;
private $JmlKare;
private $JmlTeh;
private $JmlJeruk;
private $JmlMarimas;

  public function setJumlahMakan($JmlRawon,$JmlSoto,$JmlKare){
  $this->JmlRawon = $JmlRawon;
  $this->JmlSoto = $JmlSoto;
  $this->JmlKare = $JmlKare;
 }

 public function setJumlahMinum($JmlTeh,$JmlJeruk,$JmlMarimas){
  $this->JmlTeh = $JmlTeh;
  $this->JmlJeruk = $JmlJeruk;
  $this->JmlMarimas = $JmlMarimas;
 }

 public function getJmlRawon()
 {
   return $this->JmlRawon;
 }
 public function getJmlSoto()
 {
   return $this->JmlSoto;
 }
 public function getJmlKare()
 {
   return $this->JmlKare;
 }
 public function getJmlTeh()
 {
   return $this->JmlTeh;
 }
 public function getJmlJeruk()
 {
   return $this->JmlJeruk;
 }
 public function getJmlMarimas()
 {
   return $this->JmlMarimas;
 }
}

class Transaksi extends Total {

  function __construct($detail,$produk)
  {
    $this->detail = $detail;
     $this->produk = $produk;
  }

 public function getHargaMakan() {
  $this->totalHargaRawon = $this->produk->getHargaRawon() * $this->detail->getJmlRawon();
  $this->totalHargaSoto = $this->produk->getHargaSoto()* $this->detail->getJmlSoto();
  $this->totalHargaKare = $this->produk->getHargaKare()* $this->detail->getJmlKare();
  $this->totalMakan = $this->totalHargaRawon + $this->totalHargaSoto + $this->totalHargaKare;
 }

  public function getHargaMinum() {
  $this->totalHargaTeh = $this->produk->getHargaTeh() * $this->detail->getJmlTeh();
  $this->totalHargaJeruk = $this->produk->getHargaJeruk()* $this->detail->getJmlJeruk();
  $this->totalHargaMarimas = $this->produk->getHargaMarimas()* $this->detail->getJmlMarimas();
  $this->totalMinum = $this->totalHargaTeh + $this->totalHargaJeruk + $this->totalHargaMarimas;
 }
  public function setTotalSeluruh() {
  $this->totalSeluruh = $this->totalMakan + $this->totalMinum;
 }

 public function getDetail() {
  return $this->detail;
 }

 public function Finaltotal() {
  echo "===============================================";
  echo "<br>";
  echo "=============== Struk Total Pembelian ===============";
  echo "<br>";
  echo "Total Harga Makanan = Rp. ".$this->totalMakan.",-";
  echo "<br>";
  echo "<br>";
  echo "Total Harga Minuman = Rp. ".$this->totalMinum.",-";
  echo "<br><br>";
  echo "Total Keseluruhan = Rp. ".$this->totalSeluruh.",-";
  echo "<br>";
  echo "=================Terima Kasih====================";
  echo "<br>";
  echo "===============================================";
  echo "<br>";
 
  echo "<script>window.print()</script>";
 }
}

 ?>