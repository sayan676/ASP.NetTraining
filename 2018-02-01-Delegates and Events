using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace SayanFeb1
{
    class EventExample
    {
        public delegate void CountdownDelegate();
        public event CountdownDelegate MyEvent;
        public void Countdown()
        {
            int a = 1;
            while (a <= 10)
            {
                System.Threading.Thread.Sleep(500);
                Console.WriteLine(a);
                a++;
                if (a == 11)
                    if(MyEvent!=null)
                        MyEvent();
            }
        }
        public void RaiseEvent()
        {
            Console.WriteLine("Count Down Ends");
        }
        public void Display()
        {
            Console.WriteLine("Do Something");
        }
        static void Main(string[] args)
        {
            EventExample obj = new EventExample();
            CountdownDelegate cd = new CountdownDelegate(obj.Countdown);
            cd += obj.Display;
            //cd += obj.RaiseEvent;
            obj.MyEvent += new CountdownDelegate(obj.RaiseEvent);
            obj.MyEvent += new CountdownDelegate(obj.Display);
            cd();
            Console.ReadKey(false);
        }
    }
}
