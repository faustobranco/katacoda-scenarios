# Use of lambda in List of Dicts:

Copy the code and execute in the terminal on the side.


Now it is applying the same concepts to a list of Dicts:

    lst_dict_IPs = [{'IP': '21.96.62.214', 'Link': False, 'Exists': False, 'Path': '/mnt/heapdump'},
                    {'IP': '21.96.62.214', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/saved_caches'},
                    {'IP': '21.96.62.214', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/hint'},
                    {'IP': '21.96.62.214', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/commitlog'},
                    {'IP': '253.102.1.103', 'Link': False, 'Exists': False, 'Path': '/mnt/heapdump'},
                    {'IP': '253.102.1.103', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/saved_caches'},
                    {'IP': '253.102.1.103', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/hint'},
                    {'IP': '253.102.1.103', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/commitlog'},
                    {'IP': '122.190.69.93', 'Link': False, 'Exists': False, 'Path': '/mnt/heapdump'},
                    {'IP': '122.190.69.93', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/saved_caches'},
                    {'IP': '122.190.69.93', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/hint'},
                    {'IP': '122.190.69.93', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/commitlog'},
                    {'IP': '174.40.30.197', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/saved_caches'},
                    {'IP': '174.40.30.197', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/hint'},
                    {'IP': '174.40.30.197', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/commitlog'},
                    {'IP': '226.14.168.44', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/saved_caches'},
                    {'IP': '226.14.168.44', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/hint'},
                    {'IP': '226.14.168.44', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/commitlog'},
                    {'IP': '222.53.239.60', 'Link': False, 'Exists': False, 'Path': '/mnt/heapdump'},
                    {'IP': '222.53.239.60', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/saved_caches'},
                    {'IP': '222.53.239.60', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/hint'},
                    {'IP': '222.53.239.60', 'Link': False, 'Exists': False, 'Path': '/mnt/cassandra/commitlog'}]



Use the filter to filter a single value:

    lst_ReturnFilter = list(filter(lambda d: d.get('IP') == '222.53.239.60', lst_dict_IPs))
    print(lst_ReturnFilter)


Use the filter to filter a list of values:


    list_Filter = ['174.40.30.197', '222.53.239.60']
    lst_ReturnFilter = list(filter(lambda element: element.get('IP') in list_Filter, lst_dict_IPs))
    print(lst_ReturnFilter)



Sorted with a single value:

    print(sorted(lst_dict_IPs, key=lambda element: element['IP']))

Or Sorted with a list of values:

    print(sorted(lst_dict_IPs, key=lambda element: (element['IP'], element['Path'])))


Example of using Lambda with Functions:

    def iptoint(ip):
        h = list(map(int, ip.split(".")))
        return (h[0] << 24) + (h[1] << 16) + (h[2] << 8) + (h[3] << 0)


    print(sorted(lst_dict_IPs, key=lambda element: iptoint(element['IP'])))


Extract Values to List

    print(list(map(lambda element: element.get('IP', None), lst_dict_IPs)))