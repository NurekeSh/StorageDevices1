namespace Cs;

class Program
{
    static void Main(string[] args)
    {
        // Создание объекта HardDrive
            HardDrive hardDrive = new HardDrive
            {
                Capacity = 1024,
                Speed = 150
            };
            hardDrive.StoreData(); // Вызов метода StoreData для жёсткого диска

            // Создание объекта FlashDrive
            FlashDrive flashDrive = new FlashDrive
            {
                Capacity = 64,
                UsbType = "USB 3.0"
            };
            flashDrive.StoreData(); // Вызов метода StoreData для флеш-накопителя
        }
    }

    abstract class StorageDevice 
    {
        public int Capacity { get; set; }
        public abstract void StoreData();
    }

    class HardDrive : StorageDevice
    {
        public int Speed { get; set; }

        public override void StoreData()
        {
            Console.WriteLine($"Сообщение о сохранении данных на жёстком диске. Ёмкость: {Capacity} ГБ, скорость записи: {Speed} МБ/с.");
        }
    }

    class FlashDrive : StorageDevice
    {
        public string UsbType { get; set; }

        public override void StoreData()
        {
            Console.WriteLine($"Сообщение о сохранении данных на флеш-накопитель. Ёмкость: {Capacity} ГБ, тип USB: {UsbType}.");
        }
    }


